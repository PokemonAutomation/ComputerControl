# Tutorial to Build a Home Box Sorter Program

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

If you have any questions following the tutorial, feel free to ask us in [our Discord server](https://discord.gg/cQ4gWxN).

**Tutorial to Build a Home Box Sorter Program:**

- Build the source code of our [codebase](https://github.com/PokemonAutomation/Arduino-Source/tree/main/SerialPrograms). See the [Git guide](Git.md) for how to download and prepare for source code version control. If successful, you can run the built program **SerialPrograms(.exe)** to run existing automation programs.

- To write a Home box sorter program, the easiest way is to study the existing SwSh box sorter program
[**PokemonSwSh_BoxReorderNationalDex**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonSwSh/Programs/General/PokemonSwSh_BoxReorderNationalDex.h).
The program first goes through each Pokémon in the boxes to read their names, then uses the loaded national dex order to sort the read Pokémon. Finally it swaps Pokémon locations in a loop until the box order matches the dex order.

- Copy the code in **PokemonSwSh_BoxReorderNationalDex** to create a new program listed in SerialPrograms/Source/PokemonHome/Programs/ and compile it. If successful, you can run **SerialPrograms** and notice a new program appears under the *Home* panel.

- Unlike the SwSh box sorter program, a Home box sorter program can read each Pokémon's national dex ID on its summary screen. So change some of the button commands in the copied code so that the program can enter each Pokémon's summary screen. You can use commands defined in [NintendoSwitch_Commands_PushButtons.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/NintendoSwitch/Commands/NintendoSwitch_Commands_PushButtons.h) to control the game. Example button commands are `pbf_press_button()` and `pbf_press_dpad()`.

- Write code to read national dex ID on the summary screen.
	- When a `pbf` function is called, the program does not wait for the micro-controller to finish the button command. It just sends the command to the micro-controller and continues executing following lines of code. So to make sure the summary screen is opened when the program starts reading national dex ID, use `context.wait_for_all_requests()`. This function stops the program from doing anything until all the commands sent to the micro-controller have finished. See the [button topic page](Button.md) for more details.
	- When reading info on the screen, you can use `extract_box_reference(screen, box)` to get a crop of the screen. After that, call `OCR::read_number(console, cropped_image)` to visually read numbers on the crop. See [**PokemonBDSP_BattleBallReader**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonBDSP/Inference/Battles/PokemonBDSP_BattleBallReader.cpp) as an example of how to read numbers.

- Test national dex ID reading. Now you can try printing or logging the read national dex IDs for a few Pokémon to see if the code is correct.

- Write code to do the sorting and ordering. The code for sorting read Pokémon's dex IDs and ordering the Pokémon by swapping their locations is already in **PokemonSwSh_BoxReorderNationalDex**. Change this code so that it works on Pokémon Home. After this is done, you will have a full Home box sorter program!

- Test the program. Try first debugging on a few Pokémon in the same box, then expand tests for more than one box.

- Congratulations! You now have a working Home box sorter program!

- If you would like to publish the program to our users, there is also a need to write a wiki for the program so that users know how to use it! Our program wiki is actually a Github repo [**ComputerControl**](https://github.com/PokemonAutomation/ComputerControl). Each wiki page is written as a .md file in the repo. It should be fairly easy to learn the .md writing format. You can use the same Github development cycle in the [Git guide](Git.md) to submit your new wiki page.

- This is probably not needed by a Home box sorter program, but if you want to add a new resource file (like a JSON file or an image file) to the project, you also need to upload the resource file to our [Resources Github repo](https://github.com/PokemonAutomation/Packages/tree/master/SerialPrograms/Resources). You can use the same Github development cycle in the [Git guide](Git.md) to submit your new data file.

Bonus task:
- Read more info from the summary screen so that you can sort genders and forms too. You can use the color of the gender label to detect genders. See [**PokémonLA_SkipToFullMoon**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_SkipToFullMoon.cpp) for how to read colors. 