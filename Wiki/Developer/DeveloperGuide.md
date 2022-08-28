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
	- Basic knowledge of templates.
	- Basic C++ STL classes like std::string, std::vector, std::map.
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
