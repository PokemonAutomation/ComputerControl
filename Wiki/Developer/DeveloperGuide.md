# Beginner Guide for Contributing to Pokémon Automation

## Requirement of development knowledge

If you are not familiar with several items in the requirement list, you can still develop programs, as long as you can learn them if needed. There are many online resources that help you learn C++.

- Know how to use a build tool (e.g. CMake, Visual Studio, VS Code, Qt Creator) to build and run a C++ program.
- Know basic usage of source control tool git.
- Know basic computer science concepts:
	- Programming concepts like compiling, linking and libraries.
	- Algorithm concepts like sorting, recursion, time complexity and parallelism.
- Know basic C++ language features:
	- Variables, functions, pointers, if-statement, for-loop, while-loop.
	- Variable reference, function pass-by-value vs. pass-by-reference.
	- Source files, header files, namespaces.
	- Basic C++ STL classes like std::string, std::vector, std::map.
	- Classes, objects, inheritance, abstract classes.
	- Basic knowledge of templates.
	- Exception handling.
	- Lambda functions.
- Know basic programming practices:
	- How to debug.
	- How to search for variable and function definition, declaration and usage.
	- Write comments and documents.
	- Other basic coding styles and guildlines like:
		- Don't use goto.
		- Always use {} for if, for and while statements.

## Step-By-Step Guide to Build a Home Box Sorter Program

If you have any questions following the guide, feel free to ask us in the Discord server.

- Build the source code of computer controlled programs https://github.com/PokemonAutomation/Arduino-Source/tree/main/SerialPrograms. If successful, you can run the built program **SerialPrograms** to do automation.

- To write a Home box sorter program, the easiest way is to study the existing SwSh box sorter program
[**PokemonSwSh_BoxReorderNationalDex**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonSwSh/Programs/General/PokemonSwSh_BoxReorderNationalDex.cpp).
The program first goes through each Pokémon in the boxes to read their names, then uses the loaded national dex order to sort the read Pokémon. Finally it swaps Pokémon locations in a loop until the box order matches the dex order.

- Copy the code in **PokemonSwSh_BoxReorderNationalDex** to create a new program listed in SerialPrograms/Source/PokemonHome/Programs/ and compile it. If successful, you can run **SerialPrograms** and notice a new program appears under the *Home* panel.

- Unlike the SwSh box sorter program, a Home box sorter program can read each Pokémon's national dex ID on its summary screen. So change some of the button commands in the copied code so that the program can enter each Pokémon's summary screen. You can use commands defined in [NintendoSwitch_Commands_PushButtons.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/NintendoSwitch/Commands/NintendoSwitch_Commands_PushButtons.h) to control the game. Example button commands are `pbf_press_button()` and `pbf_press_dpad()`.

- Write code to read national dex ID on the summary screen.
When `pbf_xxx()` is called, the program does not wait for the micro-controller to finish the button commands. It just sends the command to the micro-controller and continues executing following lines of code. So to make sure the summary screen is opened when the program starts reading national dex ID, use `context.wait_for_all_requests()`. This function stops the program from doing anything until all the commands sent to the micro-controller have finished.
When reading info on the screen, you can use `extract_box_reference(screen, box)` to get a crop of the screen. After that, call `OCR::read_number(console, cropped_image)` to visually read numbers on the crop. See [**PokemonBDSP_BattleBallReader**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonBDSP/Inference/Battles/PokemonBDSP_BattleBallReader.cpp) as an example of how to read numbers.

- Test national dex ID reading. Now you can try printing or logging the read national dex IDs for a few Pokémon to see if the code is correct.

- Write code to do the sorting and ordering. The code for sorting read Pokémon's dex IDs and ordering the Pokémon by swapping their locations is already in **PokemonSwSh_BoxReorderNationalDex**. Change this code so that it works on Pokémon Home. After this is done, you will have a full Home box sorter program!

- Test the program. Try first debugging on a few Pokémon in the same box, then expand tests for more than one box.

- Congratulations! You now have a working Home box sorter program!

Bonus task:
- Read more info from the summary screen so that you can sort genders and forms too. You can use the color of the gender label to detect genders. See [**PokémonLA_SkipToFullMoon**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_SkipToFullMoon.cpp) for how to read colors. 


## Introduction to Program Components

**Writing of this chapter is work in progress.**

Intoducing various components like color detection, image matching, sound detection and parallel execution to help you develop an advanced automation program!

### Access Regions of Interest on Images

To detect sth. from the video stream, we first need to know where it will appear on the screen. We usually first use `extract_box_reference()` to extract a sub-image as the region of interest from the Switch console video stream. An example is in the program
[**PokemonSwSh_BoxReorderNationalDex**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonSwSh/Programs/General/PokemonSwSh_BoxReorderNationalDex.cpp).

The function name has `reference` because it actually returns a view based on the original image: no pixels are copied in memory. It is the same "view"-like mechanism used for matrices in OpenCV and numpy.

If necessary, see Section **Wait for Some Time** to wait for the video stream to be ready for detection first.

#### Design Box Crops

To specify the location of the sub-image, we use [`ImageFloatBox`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/ImageTools/ImageBoxes.h). If you know a bit about Python, we have Python helper scripts for you to generate those boxes. Use [image_viewer.py](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Scripts/image_viewer.py) to draw initial locations of boxes:
```
python3 Arduino-Source/SerialPrograms/Scripts/image_viewer.py <path_to_an_image>
```
See docstring of `image_viewer.py` to know how to use it.

Then use [check_detector_regions.py](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Scripts/check_detector_regions.py) to fine-tune the box placements
```
python3 Arduino-Source/SerialPrograms/Scripts/check_detector_regions.py <path_to_an_image>
```
by hardcoding the box values in this script and let it render those boxes for you to inspect.

#### Render Boxes as Overlays

When automation programs are running, sometimes you can see boxes of various colors rendered on top of the video stream. Those boxes are the inference boxes used by the program to get sub-image views for visual detection. They are rendered as video overlay for developers to debug and for users to have a sense of what the program is trying to detect at the time.

To render the boxes, an example is in rendering MMO detection boxes in [PokemonLA_OutbreakFinder.cpp](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_OutbreakFinder.cpp):

Inside this program it defines a `VideoOverlaySet`:
```
VideoOverlaySet mmo_overlay_set(env.console);
```

When you call `VideoOverlaySet::add()` to add a box to it, it will automatically add the box to the video overlay so it can be rendered on the video stream. When this object is destroyed or `VideoOverlaySet::clear()` is called, all the boxes added by this object are removed from the overlay.

In order to have enough time to see the boxes rendered on the overlay, make sure this `VideoOverlaySet` object gets enough life time during program execution. You don't want this box to appear for only one frame on the overlay UI.


### Wait for Some Time

Before doing any visual or audio detection you would want to make sure the game is advanced to the desired stage. For example, you don't want to start reading Pokémon information before the game opens the Pokémon summary screen.

To let the program wait for the button commands issued by the program to finish, use `context.wait_for_all_requests()`.

You can also use `context.wait_for(std::chrono::milliseconds())` to let the program wait for a set amount of time.
There is also a function in the `pbf` button command family, `pbf_wait()`, that you can use to tell the micro-controller to wait for a specified number of ticks (Inside the micro-controller 125 ticks is one second. Access this number via [`TICKS_PER_SECOND`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/Common/NintendoSwitch/NintendoSwitch_ControllerDefs.h)).
But remember to call `context.wait_for_all_requests()` after that to make sure the computer program also waits for the `pbf_wait()` command to finish.

