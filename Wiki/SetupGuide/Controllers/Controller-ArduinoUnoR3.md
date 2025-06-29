# Controller Setup: Arduino Uno R3

The wired controller setup is the most difficult of the setups. Most of you who joined us prior to 2025 will be familiar with this setup.

This version of the wired controller setup uses the Arduino Leonardo. The hardware setup is visually identical to the Leonardo, but the firmware installation is completely different.

The Arduino Uno R3 is the legacy setup that we support only because we (barely*) still can. If you already one, then use this guide. If not, go buy an [Arduino Leonardo](Controller-ArduinoLeonardo.md) instead.

<img src="../Images/ControllerSetup-UnoR3.jpg" height="350"> <img src="../Images/ControllerSetup-Leonardo-Setup.jpg" height="350">

*The problem with the Uno R3 is that the ATmega16U2 USB chip has so little memory that is has caused us numerous problems in the past. While we have mostly mitigated these issues, we cannot guarantee that they will return in the future.

## Hardware Setup:

**Required Hardware (Full List):**
1. A regular [Nintendo Switch](../README.md#video-capture-card-the-computers-eyes) and its accessories (dock, power cable, HDMI cable). (You cannot use a Switch Lite.)
2. A [computer](../README.md#the-computer-the-player) running x64 Windows. (or another OS if you are able to set it up.)
3. A [video capture card](../README.md#video-capture-card-the-computers-eyes).
4. An [Arduino Uno R3](https://docs.arduino.cc/hardware/uno-rev3).
5. A USB-A to USB-B cable.
6. USB to Serial TTL (UART)
7. Male-Male Jumper Wires

#1-3 are part of the initial setup so you should have all of these already. #4-7 are specific to this controller setup.

**Estimated Total Cost (USD):** (not including computer and Nintendo Switch)
- **Single Setup:** $33 - $43
- **Bulk Purchase:** $29 per setup

### Recommended Purchase Links:

**Capture Card:** [See previous section.](../README.md#video-capture-card-the-computers-eyes)

**Arduino Uno R3:**

None. We do not recommend using the Uno R3. If you already have one, then please proceed. If you don't, then go for the [Arduino Leonardo](Controller-ArduinoLeonardo.md) instead.

**A USB-A to USB-B cable:**

These are super common and you probably already have a bunch of them sitting around. Otherwise just google for it.

**USB to Serial TTL (UART):**

There are many options here. The one we recommend (for ease of use) is the Adafruit model:
  - https://www.adafruit.com/product/954
  - https://www.digikey.com/en/products/detail/adafruit-industries-llc/954/7064488
  - https://www.amazon.com/dp/B00DJUHGHI/

<img src="../Images/ControllerSetup-UART-Adafruit.jpg" height="200">

Or you can search for "CP2102" and you'll get tons of hits from various brands/sellers that look like these:

<img src="../Images/ControllerSetup-UART-CP210x-Blue.png" height="150"> <img src="../Images/ControllerSetup-UART-CP210x-Red.jpg" height="150">

**Important:**

**DO NOT get cables with the Prolific controllers. e.g. PL2303 or any other model number.** They are cheap, do not work, and they are explicitly blocked in the program. **They often look deceptively similar to the Adafruit UART, but they are not the same.** If you buy outside of this link, verify it does not use PL controllers. If you buy it anyway, you will be wasting your time and money. **YOU HAVE BEEN WARNED!**

<img src="../Images/ControllerSetup-UART-NoProlific.png" height="500">


**Male-Male Jumper Wires:**
  - https://www.digikey.com/en/products/detail/twin-industries/TW-MP-10/2116120
  - https://www.amazon.com/dp/B07S1NGQR1

If purchasing the items from this list, you will need Male to Male Jumper wires.
**WARNING:** If you do ***not*** buy Hardware from this list, you will need to evaluate what you purchased for the correct type of Jumper Wire. e.g. Female-Male jumper wires may be needed instead.

<img src="../Images/ControllerSetup-UART-JumperCables.jpg" height="200">


### Hardware Assembly:

Once you have your hardware, you need to make some connections between your UART cables and the Uno R3. Use the jumper wires you bought to connect the two.

**Step 1: Connect UART to the Uno R3**

Make the following connections:
| **UART pin** | **Adafruit UART Wire Color** | **Arduino Leonardo pin** |
| --- | --- | --- |
| TX | Green | RX <- 0 (pin0) |
| RX | White | TX -> 1 (pin1) |
| GND | Black | GND (any one is fine) |
| VCC | Red | Leave unconnected |

> **If you did **not** buy the Adafruit UART, your wire colors will be different!** Refer to your UART's manual or board for the correct pins. Often, with CP210x modules, the pin type is written on the board itself. Also, note that the color of the jumper wires do not matter.

<img src="../Images/ControllerSetup-UnoR3-Wiring-0.jpg" height="300"> <img src="../Images/ControllerSetup-UnoR3-Wiring-1.jpg" height="300">


**Step 2: Download and install FLIP**

Download and install [FLIP](https://www.microchip.com/developmenttools/ProductDetails/flip).

**Step 3: Flash PABotBase into your Device.**

The root folder of the SerialPrograms package should have a set of .hex files for each of the different devices.

<img src="../Images/GeneralSetup-CCFolder.png" height="400">

1. Run the FLIP program that you downloaded earlier.
2. `Device` -> `Select`. Select `ATmega16U2` and click OK.
3. `File` -> `Load HEX File...`. Open the .hex named `NintendoSwitch-PABotBase-xxxxxxxxx-ArduinoUnoR3.hex`.

<img src="../Images/ControllerSetup-UnoR3-FLIP-0.png" height="400">

4. Plug the Arduino into your computer.
5. Short the following two pins with a conductive object, then release it. Your computer should play the unplug/plug sound.

<img src="../Images/ControllerSetup-UnoR3-ResetPins-0.jpg" height="200"> <img src="../Images/ControllerSetup-UnoR3-ResetPins-1.jpg" height="200">

6. Click on the USB icon. Select `USB` and click `Open`.

If everything worked correctly, it should look like this:

<img src="../Images/ControllerSetup-UnoR3-FLIP-1.png" height="400">

If you get an error, then it usually means one of the following:
1. The ATmega16u2 driver hasn't been correctly installed.
2. Your Arduino cannot enter DFU mode.
3. Your computer allowing the Arduino to enter DFU mode.

If it is #2, then your board is defective and cannot be used to run programs in this package.
If it is #3, we still do not know the cause. There are reports that an Arduino works on one computer, but not another.

Many people get stuck at this point if an error occurs.

Debugging this can be tricky as you will need to open up Device Manager to see if the computer recognizes the device. Then you will need to mess with the drivers.
We won't go into too much detail on how to debug things at this point. This is one of the major reasons why we are moving away from the Arduino Uno R3.

7. Click Run.

<img src="../Images/ControllerSetup-UnoR3-FLIP-2.png" height="400">

If you see no errors, the you have successfully flashed the program to your Arduino!

8. Unplug the Arduino from your computer.

**Step 4:**

1. Turn on your Switch and dock it.
2. Connect your Arduino Leonardo to the Switch's dock.
3. Connect the UART to your computer.

At this point, your final setup should look like this: (but with an Uno R3 instead of a Leonardo)

<img src="../Images/ControllerSetup-Leonardo-Setup.jpg">



## Software Setup:

Continue to: [Wired Controller (AVR8) Software Setup](Controller-Software-AVR8.md).


<hr>

**Credits:**
- Kuroneko/Mysticial

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


