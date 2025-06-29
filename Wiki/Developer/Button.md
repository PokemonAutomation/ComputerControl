# Send Button Commands

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

We mostly use a group of functions with prefix `pbf_` to send buttong commands to a micro-controller (like Arduino or Teensy). 
The controller then sends the button commands to a connected Nintendo Switch to control a game.
Those functions are defined in [NintendoSwitch_Commands_PushButtons.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/NintendoSwitch/Commands/NintendoSwitch_Commands_PushButtons.h).
Example button commands are `pbf_press_button()` and `pbf_press_dpad()`.
You can read the comments of those functions to understand how to use them.

Note we use ticks to measure the amount of time a button action is executed. Inside the micro-controller 125 ticks is one second. Access this number via [`TICKS_PER_SECOND`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/Common/NintendoSwitch/NintendoSwitch_ControllerDefs.h).

An example automation program that uses those functions is [**PokemonLA_BraviaryHeightGlitch**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_BraviaryHeightGlitch.cpp).

## Button Command Buffer on Micro-Controller

When a `pbf` function is called, the program may not wait for the micro-controller to finish executing the button command.
It may just send the command to the micro-controller and continue executing following lines of code.
Our software that runs on the micro-controller uses a buffer to hold incoming button commands.
The `pbf` function has to wait only when the buffer on the micro-controller is full. It will wait until the micro-controller finishes executing the oldest command in the buffer so that the buffer has space to receive the new command.*

For example, if the micro-controller buffer is empty and a program sends a command of holding button A for 200 ticks and releasing it for 100 ticks,
the program will not wait for 300 ticks during exeuction of `pbf_press_button()`.
The function quickly returns and the program begins executing the next line of code.
At the same time, the micro-controller will start spending 300 ticks to execute the button command.
It will keep pressing button A to the Switch for 200 ticks, then release it and wait for 100 ticks.

This is like the case of asynchronous IO processing in some software systems.

**Important:** You should not *rely* this asynchronous behavior to perform parallelization. The internal buffer sizes are undocumented and may change at any time. And some functions may break into a sequence of instructions that occupy multiple buffer slots. The purpose of the asynchronous buffering is to preserve the exact timing of button sequences across an otherwise high-latency serial bus.

## Wait for Commands to Finish

So in the case like you would want the program to wait for the button commands to finish before doing some other tasks (e.g. reading the video stream),
you need to call `context.wait_for_all_requests()` after the code of button commands.
This function stops the program from doing anything until all the commands sent to the micro-controller have finished.
An example usage is in [**PokemonLA_PokedexTasksReader**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_PokedexTasksReader.cpp).
The program reads Pokédex tasks. After it sends button commands that tells the game to go to the next Pokédex page,
it calls `context.wait_for_all_requests()` before reading the video stream. In this way, when the program reads the video stream, the game is indeed showing the next page.
