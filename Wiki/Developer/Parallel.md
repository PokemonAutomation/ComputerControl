# Parallel Routines

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

Sometimes we would like to achieve the following actions:
- Wait for the game to start a battle.
- Move the player character in circles until an egg is hatching.

To wait for a visual or audio event, we use `wait_until()`.
To send some button commands until a visual or audio event happens, we use `run_until()`.
Both functions are declared in [InferenceRoutines.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/InferenceInfra/InferenceRoutines.h). An example usage of both functions is in [`mash_A_to_change_region()`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/PokemonLA_RegionNavigation.cpp).

## wait_until()

When `wait_until()` is called, the main thread that executes this function call is suspended.
Another inference thread is used to periodically execute some visual or audio inference code.
If the inference code returns true, then the wait is over, the main thread wakes up and the inference thread finishes.
If the wait times out, the main thread also wakes up and the inference thread finishes.

You can pass a `vector` of `PeriodicInferenceCallback` to the function.
Those callbacks are the visual or audio inference
objects.
The base class for a callback object is [`InferenceCallback`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/InferenceInfra/InferenceCallback.h).
The base visual inference callback class is [`VisualInferenceCallback`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/InferenceInfra/VisualInferenceCallback.h).
The base audio inference callback class is [`AudioInferenceCallback`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/InferenceInfra/AudioInferenceCallback.h).

To write a new visual inference class, inherit `VisualInferenceCallback`.
An example is [`BlackScreenOverWatcher`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/Inference/BlackScreenDetector.h) used in `mash_A_to_change_region()`.
For each inference object passed to `wait_until()`, `wait_until()` calls the object's `process_frame()` to do the inference work.
If the function returns true, the wait is also over.
`wait_until()` also calls the object's `make_overlays()` to visualize the inference (usually by rendering some boxes on the target regions of the video stream) on the video overlay.

When `wait_until()` returns, if it times out, it returns -1.
Otherwise, it returns the index of the callback object in the `vector` of `PeriodicInferenceCallback` that returns true to stop the loop.

## run_until()

When `run_until()` is called, a command thread is used to run the `command` function that usually sends button commands like mashing A in the case of `mash_A_to_change_region()`.
Another inference thread is used to periodically execute some visual or audio inference code like checking when the black screen is over in the case of `mash_A_to_change_region()`.
If the inference code returns true, then the run is over, the command thread stops the button command function immediately and the inference thread finishes.
If the button command function finishes execution, the run is also over, both two threads finish and the main thread moves on.

Like `wait_until()`, the function accepts a `vector` of `PeriodicInferenceCallback` for the inference thread to execute.
See `mash_A_to_change_region()` again as an example.

When `run_until()` returns, if it returns because the button command function finishes, it returns -1.
Otherwise, it returns the index of the callback object in the `vector` of `PeriodicInferenceCallback` that returns true to stop the loop.

For the usage of an audio inference callback, see [**PokemonLA_UnownFinder**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/ShinyHunting/PokemonLA_UnownFinder.cpp).

## Race Condition

Because it involves multithreading, you need to be careful not to create race conditions. For example, don't let the inference thread and the button command thread in `run_until()` access the same variable without a lock.
