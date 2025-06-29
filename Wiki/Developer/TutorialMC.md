# Tutorial to Build a Button Script Program

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

If you have any questions following the tutorial, feel free to ask us in [our Discord server](https://discord.gg/cQ4gWxN).

**Tutorial to Build a Button Script Program:**

This tutorial lets you write code that can send a series of hardcoded button commands to Switch to control a game.
Function-wise it's like a programmable smart Switch controller.
Note it is a non-feedback program because no video or audio detection is used.

- Build the source code of our [codebase](https://github.com/PokemonAutomation/Arduino-Source/tree/main/SerialPrograms). See the [Git guide](Git.md) for how to download and prepare for source code version control. If successful, you can run the built program **SerialPrograms(.exe)** to run existing automation programs. 

- To write a new program, the easiest way is to study the existing non-feedback program
[**PokemonLA_BraviaryHeightGlitch**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_BraviaryHeightGlitch.h).
The program applys an exploit while the player character rides on Braviary so that the player can gain unlimited height in the overworld.
See its [Wiki page](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonLA/BraviaryHeightGlitch.md) on how to use the program.

	- A more complex program example is [**PokemonLA_ApplyGrits**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_ApplyGrits.h) ([Wiki](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonLA/ApplyGrits.md)).

- Copy the code in **PokemonLA_BraviaryHeightGlitch** to create a new program listed in SerialPrograms/Source/PokemonLA/Programs/ and compile it. If successful, you can run **SerialPrograms** and notice a new program appears under the *LA* panel.

- Change the code in function `BraviaryHeightGlitch::program()` to add your own code by trying some `pbf_xxx()` function calls. Those functions send button commands to Switch. They are defined in [NintendoSwitch_Commands_PushButtons.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/NintendoSwitch/Commands/NintendoSwitch_Commands_PushButtons.h) to control the game. Example button commands are `pbf_press_button()` and `pbf_press_dpad()`. You can read the comments of those functions to understand how to use them.

- Compile the program and test it on your Switch.

- Congratulations! You now have a working Switch controller button script program! You can write button sequence of arbitrary complexity to control your Switch game!

- If you find an interesting use case of your script in one of the Pokémon games, you are welcome to submit this script to our team to be used by our users. See the [Git guide](Git.md) for how to submit code.

	- After your new program is accepted to our codebase, there is also a need to write a wiki for the program so that users know how to use it! Our program wiki is actually a Github repo [**ComputerControl**](https://github.com/PokemonAutomation/ComputerControl). Each wiki page is written as a .md file in the repo. It should be fairly easy to learn the .md writing format. You can use the similiar Github development cycle in the [Git guide](Git.md) to submit your new wiki page.