# Access Regions of Interest on Images

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

To detect something from the video stream, we first need to know where it will appear on the screen. We usually first use `extract_box_reference()` to extract a sub-image as the region of interest from the Switch console video stream. An example is in the program
[**PokemonSwSh_BoxReorderNationalDex**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonSwSh/Programs/General/PokemonSwSh_BoxReorderNationalDex.cpp).

The function name has `reference` because it actually returns a view based on the original image: no pixels are copied in memory. It is the same "view"-like mechanism used for matrices in OpenCV and numpy.

If necessary, see Section **Wait Some Time** to wait for the video stream to be ready for detection first.

## Design Box Crops

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

## Render Boxes as Overlays

When automation programs are running, sometimes you can see boxes of various colors rendered on top of the video stream. Those boxes are the inference boxes used by the program to get sub-image views for visual detection. They are rendered as video overlay for developers to debug and for users to have a sense of what the program is trying to detect at the time.

To render the boxes, an example is in rendering MMO detection boxes in [PokemonLA_OutbreakFinder.cpp](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_OutbreakFinder.cpp):

Inside this program it defines a `VideoOverlaySet`:
```
VideoOverlaySet mmo_overlay_set(env.console);
```

When you call `VideoOverlaySet::add()` to add a box to it, it will automatically add the box to the video overlay so it can be rendered on the video stream. When this object is destroyed or `VideoOverlaySet::clear()` is called, all the boxes added by this object are removed from the overlay.

In order to have enough time to see the boxes rendered on the overlay, make sure this `VideoOverlaySet` object gets enough life time during program execution. You don't want this box to appear for only one frame on the overlay UI.