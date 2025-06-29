# Command Line Tests

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

When designing visual/audio inference methods,
developers may want to test them on some test images/audios first before adding them into a program and testing the full program.
The reason is that testing a full program is difficult:
you may need to wait quite some time for one program run, and you may need to reset the game every time.
So if we can make sure an inference function works on several test images, then it will be less likely to fail in a full program.

If you would like to write some inference tests, we have a [command line test framework](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/Tests/CommandLineTests.h).
The framework is similar to unit tests. It can test each inference component individually.
The difference is: common unit tests have their own build targets.
But to save us the time of writing those build targets, we use the program setting JSON, named SerialPrograms-Settings.json to denote which tests to run. Apart from the command line test setting, the JSON file stores all the user inputs and preferences so that the **SerialPrograms** executable remembers the user data from the last session.

## Use Test Framework

Enable the command line test mode by changing the SerialPrograms-Settings.json field:
```
"20-GlobalSettings": "COMMAND_LINE_TESTS": "RUN"
```
to true. 

If you are testing or building with Qt creator, you can find SerialPrograms-Settings.json in the folder `Arduino-Source\build-SerialPrograms-Desktop_Qt_6_3_2_MSVC2019_64bit-Debug\UserSettings`, or something similar, depending on your version of Qt.

In this mode, when starting **SerialPrograms**, it does not launch the GUI. Instead it looks for a local folder the path of which is specified by the json field:
```
"20-GlobalSettings": "COMMAND_LINE_TESTS": "FOLDER"
```
and run tests inside it.
One example path is "./CommandLineTests".

Tests are not included in the Arduino-Source repository. To see some examples of test files and their folder structure, see the [CommandLineTests](https://github.com/PokemonAutomation/CommandLineTests) repository. 

To try using these tests, the value for "FOLDER" in the json should be set to "./CommandLineTests". Download/clone the CommandLineTests from the above repository, and put this folder in the `Arduino-Source\build-SerialPrograms-Desktop_Qt_6_3_2_MSVC2019_64bit-Debug` folder.

Example folder structure:
```
CommandLineTests/                          <- root test folder. This name needs to match the folder specified in "FOLDER"
- PokemonLA/                               <- test space, ususally which game the test belongs to.
  - BattleMenuDetector/                    <- test object, name of the class/function/file to test
    - IngoBattleDayTime_True.png           <- test file for BattleMenuDetector. Expected result is True.
    - IngoBattleNightTime_True.png         <- test file for BattleMenuDetector. Expected result is True.
- PokemonBDSP/                             <- another test space for inferences in another game
  - DialogDetector/                        <- test object, this time it's DialogDetector for BDSP
    - Win_Mirabox/                         <- can have more folders under test object to organize test files, e.g by OS and capture card
      - FetchEggDayTime_True.png           <- test file for DialogDetector. Expected result is True.
```

### Find Test Code for Test File

When running in the test mode, it will go to find each file in the folder recursively.
We assume each file is a test image or other test file. For each file, **it uses the file path to determine which test code to call to run on the test file**.

For example, if the path is `CommandLineTest/PokemonLA/BattleMenuDetector/`, the test framework first finds all the files inside this folder as test files.
It then finds the corresponding test code `test_pokemonLA_BattleMenuDetector()` declared in [PokemonLA_Tests.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/Tests/PokemonLA_Tests.h) and calls the test function with each test file.
To find the test code given a file path, we use a mapping defined as `TEST_MAP` in [TestMap.cpp](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/Tests/TestMap.cpp).

The expected result for the image should be in the file name at the end. E.g. if you expect the test result on the image should be true, the image name should end with `_True`.

### "Hidden" Files

In the test folder, filenames starting with "\_" are considered "hidden" files and are ignored by the test framework when searching for files.
Those "hidden" files are useful for storing some metadata in the folder.

They can also be used as an extra file in case some tests need more than one test file.
For example, we would like to read some Pokémon from Pokémon sprites on an image.
There are many Pokémon sprites, so we would like to save the target Pokémon [slugs](Slug.md) in a text file.
(This kind of file is also called "golden file" by some engineers: the file contains the desired code output that
the engineers need to fix the code to match.)
This means one test of sprite reading involves two files (one image and one text).
We set the text filename to start with "\_" so the test framework only finds the image file and 
run the test function with the image file path as the input argument.
Inside the function we can then use the input image file path to find the text file path and load the target Pokémon slugs.

### Select Tests

You can also selectively run a subset of the tests by setting
```
"20-GlobalSettings": "COMMAND_LINE_TESTS": "TEST_LIST"
```
as a list of strings. Each string will be a relative path. Example types of the path can be any of:
 - "PokemonBDSP"
 - "PokemonBDSP/DialogDetector"
 - "PokemonBDSP/DialogDetector/Win_Mirabox"
 - "PokemonBDSP/DialogDetector/Win_Mirabox/FetchEggDayTime_True.png"

This gives the flexibility to test the code for a game, a detector, a detector on a capture card or a detector on a particular image.

### Ignore Tests

If you have put some test files for experimental code in a folder and later decide to not run that code for a while,
you can use
```
"20-GlobalSettings": "COMMAND_LINE_TESTS": "IGNORE_LIST"
```
as a list of strings to skip the paths to those tests.

Each string in the list serves as a prefix to the test path that the test framework uses to filter out paths.

## Add New Tests

When adding new tests, add the new test function to both `Tests.cpp` and `Tests.h`, as well as to `TestMap.cpp`.

For example, in order to implement a test for BattleMenuDetector:
- Implement a ScreenBoolDetectorFunction, `test_pokemonLA_BattleMenuDetector()` that calls the detector code and compares the result with the target bool. The implementation is written in `PokemonLA_Tests.cpp`.
- Write the function declaration in `PokemonLA_Tests.h`
- Add a new entry to `TestMap.cpp:TEST_MAP` by utilizing screen_bool_detector_helper:
`{"PokemonLA_BattleMenuDetector", std::bind(screen_bool_detector_helper, test_pokemonLA_BattleMenuDetector, _1)}`

You can read the code of existing test functions like `test_pokemonLA_BattleMenuDetector()` to know how to write test code.

### How the test framework works

The test framework calls [`find_test_function(test_space, test_obj_name)`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/Tests/TestMap.h) to find the test function related to a test path.

For example, given a path `PokemonLA/BattleMenuDetector/IngoBattleDayTime_True.png`, by extracting `test_space` as "PokemonLA" and `test_obj_name` as "BattleMenuDetector" from the path,

`find_test_function()` returns the test code `test_pokemonLA_BattleMenuDetector()` declared in [PokemonLA_Tests.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/Tests/PokemonLA_Tests.h).
 
Internally, `find_test_function()` searches in a map: `std::map<std::string, TestFunction> TEST_MAP` to get the correct test function.
The key of the map in the above example is "PokemonLA_BattleMenuDetector" (we use "\_" to connect test space and test obj name).
The value type of the map is `TestFunction = std::function<int(const std::string& test_file_path)>.` This is the test function.

