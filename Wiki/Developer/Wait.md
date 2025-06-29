# Wait Some Time

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

Before issuing a button command or doing any visual or audio detection, you would want to make sure the game is advanced to the desired stage. For example, you don't want to start reading Pokémon information before the game opens the Pokémon summary screen.

To let the program wait for the button commands issued by the program to finish, use `context.wait_for_all_requests()`. See the [button topic page](Button.md) for more details about this function.

You can also use `context.wait_for(std::chrono::milliseconds())` to let the program wait for a set amount of time.
There is also a function in the `pbf` button command family, `pbf_wait()`, that you can use to tell the micro-controller to wait for a specified number of ticks (Inside the micro-controller 125 ticks is one second. Access this number via [`TICKS_PER_SECOND`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/Common/NintendoSwitch/NintendoSwitch_ControllerDefs.h)).
But remember to call `context.wait_for_all_requests()` after that to make sure the computer program also waits for the `pbf_wait()` command to finish.

## Important:

Do not use any of the usual C++ or OS wait functions. These include:
- `std::condition_variable::wait_xx()`
- Windows: `Sleep()`
- Linux: `usleep()`
- (any many more)

These wait functions will not wake from an external signal such as the user clicking "Stop Program" or the program detecting a shiny and needing to stop immediately before the shiny runs away.

The *only* safe way to perform a wait is to call it on a context object: `context.wait_for(...)`
This has been carefully designed to properly respond to such external signals.

# Design wait time

For example, you need to design a sequence of button commands to talk to an NPC and select an item from the dialogue menu. Starting the program in front of the NPC, you need to press A, then wait several ticks for the dialogue box to appear, and press D-pad down to move the cursor to the desired item in the menu. How many waiting ticks is enough to connect the two button presses? You can test different ticks until the automation program runs stably on your Switch. To make sure that other users who have a slower Switch than you can also run the program, it would be better to relax the wait time by a few more ticks.

But a longer wait time may make the program slower. And you don't know if the wait time is long enough for all the users. To take more care of the robustness and performance, there are several other approaches:

- Make this wait time tunable by users. Expose this wait time as a program option. This has the benefit of those with a slower Switch can set a long wait time to have robust runs while those with a faster Switch can set a short wait time to get better performance. But this adds more things for the users to do and the users may also be annoyed by tuning the wait time themselves.

- Use visual feedback (or called visual inference): use `wait_until()` (see the [parallel routine topic page](Parallel.md) for more details) and other functions to let the program wait until a visual indication is detected, signaling the dialogue menu is fully displayed. Then press the next button. This has the benefit of the program adapting to the dialogue display speed. The drawback is that it is more coding work to write visual detection code, and the program is generally slower than a fine-tuned feedback-less button sequence. It is because the program has to wait for the video frames to be parsed through the capture card and needs the visual detection code to finish running.

- Send the button press first without visual feedback, but also monitor the video stream and detect if there is deviation (overshoot or undershoot) of the menu cursor from what the program expects it to be based on the button presses. If a deviation is found, using a correction procedure to fix it. This is the most complicated to implement among all the approaches, but it is robust to different Switch speed and generally fast to run.

You can mix and match all the approaches. Use the approach that is suitable for the task. For simple and short automation tasks like mass releasing Pokémon in the storage, you can hardcode the wait times between button presses. For performance sensitive tasks like selecting Pokéballs in Dynamax Adventure, to pursue best shiny hunting performance, use the overshoot-correction mechanism.
