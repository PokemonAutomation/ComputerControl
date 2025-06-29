# Access Regions of Interest on Images

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

To detect something from the video stream, we first need to know where it will appear on the screen. We usually first use `extract_box_reference()` to extract a sub-image as the region of interest from the Switch console video stream. An example is in the program
[**PokemonSwSh_BoxReorderNationalDex**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonSwSh/Programs/General/PokemonSwSh_BoxReorderNationalDex.cpp).

The function name has `reference` because it actually returns a view based on the original image: no pixels are copied in memory. It is the same "view"-like mechanism used for matrices in OpenCV and numpy.

If necessary, see this [topic page](Wait.md) on how to wait for the video stream to be ready for detection first.

## Design Box Crops

To specify the location of the sub-image, we use [`ImageFloatBox`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/ImageTools/ImageBoxes.h).

If you know a bit about Python, we have Python helper scripts for you to generate those boxes. 

A brief guide if you haven't used Python before: Download and install Python. Ensure `pip` is included during the installation. Once installed, install opencv, by opening the terminal and typing:

```
pip install opencv-contrib-python
```

To draw the initial locations of boxes, use [image_viewer.py](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Scripts/image_viewer.py)

```
python3 Arduino-Source/SerialPrograms/Scripts/image_viewer.py <path_to_an_image>
```

Note: if there are any spaces in the path to the python script, or to the path to the image, wrap the path in parentheses.

In Windows, use `py` or `python` instead of `python3`.

To use the program, left click and drag to draw the rectangle. Press 'i' to dump the information of the drawn boxes. Press 'ESC' to exit the program. See the docstring of `image_viewer.py` for more details.

Then use [check_detector_regions.py](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Scripts/check_detector_regions.py) to fine-tune the box placements
```
python3 Arduino-Source/SerialPrograms/Scripts/check_detector_regions.py <path_to_an_image>
```
by hardcoding the box values in this script and let it render those boxes for you to inspect.

### Box Draw program

If Developer mode is enabled, the Computer Control program includes a program called `Box Draw`, under the Nintendo Switch programs.

If you specify the X and Y coordinates of the box, as well as its width and height, the box will be drawn on the screen.

## Render Boxes as Overlays

When automation programs are running, sometimes you can see boxes of various colors rendered on top of the video stream. Those boxes are the inference boxes used by the program to get sub-image views for visual detection. They are rendered as video overlay for developers to debug and for users to have a sense of what the program is trying to detect at the time.

To render the boxes, an example is in rendering MMO detection boxes in [PokemonLA_OutbreakFinder.cpp](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_OutbreakFinder.cpp):

Inside this program it defines a `VideoOverlaySet`:
```
VideoOverlaySet mmo_overlay_set(env.console);
```

When you call `VideoOverlaySet::add()` to add a box to it, it will automatically add the box to the video overlay so it can be rendered on the video stream. When this object is destroyed or `VideoOverlaySet::clear()` is called, all the boxes added by this object are removed from the overlay.

In order to have enough time to see the boxes rendered on the overlay, make sure this `VideoOverlaySet` object gets enough life time during program execution. You don't want this box to appear for only one frame on the overlay UI.

## Debug Boxes

If the data of the box is known during compile time, you can just use the Python script image_viewer.py to visualize it.
If the box is generated at runtime, you can use `draw_box()` defined in [ImageBoxes.h](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/ImageTools/ImageBoxes.h) to draw the box onto an image. You can then save the image to disk to debug it.