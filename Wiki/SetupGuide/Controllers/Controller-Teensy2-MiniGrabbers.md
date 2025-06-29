# Controller Setup: Teensy 2.0 and Teensy++ 2.0 (using mini-grabber cables)

The wired controller setup is the most difficult of the setups. Most of you who joined us prior to 2025 will be familiar with this setup.

The Teensy 2.0 or Teensy++ 2.0 have been discontinued by the manufacturer. So we do not recommend any new setups with these. Therefore, this guide is only if you already have a Teensy from our past era of microcontroller-only automation and wish to upgrade to full computer control.

This tutorial will use mini-grabber cables to connect the UART to the Teensy. While it is ugly and bulky, it is the easiest option for Teensy users who prefer not to do any soldering.

<img src="../Images/ControllerSetup-Teensy2-MiniGrabbers.jpg" height="350"> <img src="../Images/ControllerSetup-Teensy-Setup.jpg" height="350">

## Hardware Setup:

**Required Hardware (Full List):**
1. A regular [Nintendo Switch](../README.md#video-capture-card-the-computers-eyes) and its accessories (dock, power cable, HDMI cable). (You cannot use a Switch Lite.)
2. A [computer](../README.md#the-computer-the-player) running x64 Windows. (or another OS if you are able to set it up.)
3. A [video capture card](../README.md#video-capture-card-the-computers-eyes).
4. A [Teensy 2.0](https://www.pjrc.com/store/teensy.html) or [Teensy++ 2.0](https://www.pjrc.com/store/teensypp.html).
5. USB A to mini USB cable
6. USB to Serial TTL (UART)
7. Mini-Grabbers to Male Jumper Wires

### Recommended Purchase Links:

**Capture Card:** [See previous section.](../README.md#video-capture-card-the-computers-eyes)

**Teensy 2.0 or Teensy++ 2.0:**

Product has been discontinued.

**USB A to mini USB cable:**

You should already have this from prior Teensy automation.

**USB to Serial TTL (UART):**

There are many options here. The one we recommend (for ease of use) is the Adafruit model:
  - https://www.adafruit.com/product/954
  - https://www.digikey.com/en/products/detail/adafruit-industries-llc/954/7064488
  - https://www.amazon.com/dp/B00DJUHGHI/

<img src="../Images/ControllerSetup-UART-Adafruit.jpg" height="200">

Or you can search for "CP2102" and you'll get tons of hits from various brands/sellers that look like these:

<img src="../Images/ControllerSetup-UART-CP210x-Blue.png" height="150"> <img src="../Images/ControllerSetup-UART-CP210x-Red.jpg" height="150">

**Mini-Grabbers to Male Jumper Wires**
- https://www.amazon.com/gp/product/B08M5GNY47

If you choose a different UART make sure that the wire-end of the mini-grabber can plug into the UART. So if you picked the red CP2102 UART, you will want the female mini-grabber.

<img src="../Images/ControllerSetup-UART-MiniGrabber.jpg" height="350">


### Hardware Assembly:

**Step 1: Connect UART to the Teensy**

Once you have your hardware, you need to make some connections between your UART cables and the Teensy. Use the mini-grabber cables to connect them.

Make the following connections:
| **UART pin** | **Microcontroller pin** |
| --- | --- |
| TX | D2 |
| RX | D3 |
| GND | GND (any one is fine) |
| VCC | Leave unconnected |

Note that the mini grabber clips may not fit through the holes on the Teensy 2.0/Teensy++2.0. This is fine.

**Teensy 2.0:** (click on images to enlarge)

<img src="../Images/ControllerSetup-Teensy2-MiniGrabbers-0.jpg" height="350"> <img src="../Images/ControllerSetup-Teensy2-MiniGrabbers-1.jpg" height="350">

**Teensy++ 2.0:** (click on images to enlarge)

<img src="../Images/ControllerSetup-Teensypp2-MiniGrabbers-0.jpg" height="350"> <img src="../Images/ControllerSetup-Teensypp2-MiniGrabbers-1.jpg" height="350">


**Step 2: Download and install Teensy Loader**

Download [Teensy Loader](https://www.pjrc.com/teensy/loader.html).

Direct download link: https://www.pjrc.com/teensy/teensy.exe

**Step 3: Flash PABotBase into your Teensy.**

The root folder of the SerialPrograms package should have a set of .hex files for each of the different devices.

<img src="../Images/GeneralSetup-CCFolder.png" height="400">

1. Run the Teensy Loader program that you downloaded earlier.
2. Click the purple file icon and browse for `NintendoSwitch-PABotBase-xxxxxxxxx-Teensy2.hex` or `NintendoSwitch-PABotBase-xxxxxxxxx-TeensyPP2.hex` depending on which one you have.

<img src="../Images/ControllerSetup-Teensy2-Loader-0.png">

3. Plug the Teensy into your computer.
4. Press the white button on the Teensy. You may need to wait for Windows to install drivers.

At this point, two green arrows should show up in Teensy Loader.

<img src="../Images/ControllerSetup-Teensy2-Loader-1.png">

5. Click the left arrow. This flashes the program into the Teensy.

<img src="../Images/ControllerSetup-Teensy2-Loader-2.png">

6. Unplug the Teensy from your computer.

**Step 4:**

1. Turn on your Switch and dock it.
2. Connect your Teensy to the Switch's dock.
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

