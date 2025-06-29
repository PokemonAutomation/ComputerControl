# Check Color

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

A simple visual detection method is to check the color of a region of the image. See [this topic](SubImage.md) on how to get a region of the image.

We use [`image_stats()`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/ImageTools/ImageStats.h) to extract color stats from an image.
An example usage is in [PokemonBDSP_MenuDetector.cpp](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonBDSP/Inference/PokemonBDSP_MenuDetector.cpp).
`image_stats()` returns a struct `ImageStats` that stores average per-pixel color, pixel color stddev and pixel count on this image. Then it calls `is_white()` declared in [SolidColorTest.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/ImageTools/SolidColorTest.h) to check whether the stats reflect the image is all white.

We also commonly use `is_solid()` in SolidColorTest.h to check whether the image is full of a particular color. 
For example you can check [PokemonLA_DialogDetector.cpp](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Inference/PokemonLA_DialogDetector.cpp).

## Determine Color Thresholds

When doing color check, you need to set thresholds in `is_solid()` and other functions,
like what is the maximum color deviation that can still pass the check.
You can first collect a few test images by taking screenshots using the screenshot button on the **SerialPrograms** executable.
Pick some thresholds to pass all your test images.
You can add command line tests (See [its topic](Tests.md)) to run color detection on images directly without temporarily hardcoding tests.

Finally, keep the thresholds a little higher than needed on your test images so that users with different capture card color distortions than yours can still pass the check.


## Color Values

We have a `Color` class in [Color.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/Common/Cpp/Color.h) to represent a 32-bit-precision ARGB pixel color. Each color channel precision is 8-bit `uint8`. The data in `Color` is stored as a `uint32_t`. Some of our color-related functions also take `uint32_t` as color inputs. See `combine_argb()` and `combine_rgb()` in Color.h to know how individual A, R, G, B values form a `uint32_t`.

