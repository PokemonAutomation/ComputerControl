# Controller Setup: Pro Micro (using solderless hammer headers)

The wired controller setup is the most difficult of the setups. Most of you who joined us prior to 2025 will be familiar with this setup.

The Pro Micro is the recommended microcontroller to use for experimenced users. It is harder to setup than the Arduino Leonardo, but is smaller in space and cheaper in quantity for automating multiple Switches.

This tutorial will use solderless hammer headers to connect the UART to the Pro Micro. This is a cleaner, but harder setup while still avoiding any soldering.

<img src="../Images/ControllerSetup-ProMicro-HammerHeaders.jpg" height="350"> <img src="../Images/ControllerSetup-Teensy-Setup.jpg" height="350">

## Hardware Setup:

**Required Hardware (Full List):**
1. A regular [Nintendo Switch](../README.md#video-capture-card-the-computers-eyes) and its accessories (dock, power cable, HDMI cable). (You cannot use a Switch Lite.)
2. A [computer](../README.md#the-computer-the-player) running x64 Windows. (or another OS if you are able to set it up.)
3. A [video capture card](../README.md#video-capture-card-the-computers-eyes).
4. A Pro Micro microcontroller.
5. USB A to mini USB cable
6. USB to Serial TTL (UART)
7. Solderless Hammer Headers
8. A box cutter or a wire cutter.
9. Pliers. (you will likely need two of them)

**Estimated Total Cost (USD):** (not including computer, Nintendo Switch, and household tools)
- **Single Setup:** $40 - $50
- **Bulk Purchase:** $20 per setup (in quantities of 4+)

### Recommended Purchase Links:

**Capture Card:**
- [See previous section.](../README.md#video-capture-card-the-computers-eyes)

**Pro Micro:** https://www.amazon.com/gp/product/B08BJNV1J3

**USB A to micro USB cable:**
- https://www.amazon.com/Android-Compatible-Smartphones-Charging-Stations/dp/B095JZSHXQ

**USB to Serial TTL (UART):**

There are many options here. The one we recommend (for ease of use) is the Adafruit model:
  - https://www.adafruit.com/product/954
  - https://www.digikey.com/en/products/detail/adafruit-industries-llc/954/7064488
  - https://www.amazon.com/dp/B00DJUHGHI/

<img src="../Images/ControllerSetup-UART-Adafruit.jpg" height="200">

Or you can search for "CP2102" and you'll get tons of hits from various brands/sellers that look like these:

<img src="../Images/ControllerSetup-UART-CP210x-Blue.png" height="150"> <img src="../Images/ControllerSetup-UART-CP210x-Red.jpg" height="150">

**Solderless Hammer Headers**
- https://www.adafruit.com/product/3662

These "hammer headers" have a bulge on the short side which enables it to attach to pin holes without the use of solder.

<img src="../Images/ControllerSetup-UART-HammerHeaders.jpg" height="200">



### Hardware Assembly:

**Step 1: Connect UART to the Pro Micro**

Once you have your hardware, you need to make some connections between your UART cables and the Pro Micro.

Make the following connections:
| **UART pin** | **Microcontroller pin** |
| --- | --- |
| TX | RX1 |
| RX | TX0 |
| GND | GND (any one is fine) |
| VCC | Leave unconnected |

1. Use your box cutter or wire cutter to cut out 2 pairs of pins from the strip of solderless headers. ***Be very careful not to cut yourself.***
2. Insert a pair of hammer headers into the D3 and D2 holes on the Teensy.
3. Insert a hammer header into the GND hole on the microcontroller. (Since you can't easily split the pair of pins, you can do GND and the pin adjacent to it.)

You will need a LOT of force to push the hammer headers into the holes. Recommend using pliers to pull the pins out of the plastic holds and inserting the long side into the microcontroller board. Then put the covers back on and use pliers to squeeze it in.

<img src="../Images/ControllerSetup-ProMicro-HammerHeaders-0.jpg" height="350"> <img src="../Images/ControllerSetup-ProMicro-HammerHeaders-1.jpg" height="350">
<img src="../Images/ControllerSetup-ProMicro-HammerHeaders-2.jpg" height="350">


**Step 2: Download QMK Toolbox**

A few QMK versions are known to work. e.g. 0.1.1, 0.2.2, and 0.3.1. Other versions may not work (e.g. 0.3.2 does not work).

Download [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases). Ensure you download a version known to work. e.g. 0.3.1.

You want the file `qmk_toolbox.exe`. You'll find it under `Assets`, under the version number that you choose (e.g. 0.3.1).

**Step 3: Flash PABotBase into your Device.**

The root folder of the SerialPrograms package should have a set of .hex files for each of the different devices.

<img src="../Images/GeneralSetup-CCFolder.png" height="400">

1. Run the QMK Toolbox program that you downloaded in PART 2.
2. Open the .hex named `NintendoSwitch-PABotBase-xxxxxxxxx-ProMicro.hex`.
3. Change the MCU to `atmega32u4`.
4. Check the "Auto-Flash" box.

<img src="../Images/ControllerSetup-ProMicro-Flash-0.png" height="600">

5. Plug the Pro Micro into your computer.
6. Short the RST and GND pins.

<img src="../Images/ControllerSetup-ProMicro-Flash-1.jpg" height="400">

The QMK program will now flash the program to the Pro Micro and show a bunch of logging.
Afterwards, the 2 LEDs on the Pro Micro should flash in unison for 5 seconds before turning off.

<img src="../Images/ControllerSetup-ProMicro-Flash-2.png" height="600">

7. Unplug the Leonardo from your computer.

**Step 4:**

1. Turn on your Switch and dock it.
2. Connect your Pro Micro to the Switch's dock.
3. Connect the UART to your computer.

At this point, your final setup should look like this:

<img src="../Images/ControllerSetup-Teensy-Setup.jpg">


## Software Setup:

Continue to: [Wired Controller (AVR8) Software Setup](Controller-Software-AVR8.md).


<hr>

**Credits:**
- Kuroneko/Mysticial
- jw

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)



