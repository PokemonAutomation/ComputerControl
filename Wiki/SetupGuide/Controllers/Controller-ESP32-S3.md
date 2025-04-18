# Controller Setup: ESP32-S3

***This setup is still in development. Unless you are a developer, you will not be able to do this setup since you won't have access to the (work-in-progress) firmware.***

<hr>

This is the brand new wired controller setup that is much easier to do than the old AVR8 ones using Arduino or Teensy. If you are beginner, we still recommend starting with the ESP32 wireless setup. But nothing beats good old wired in its stability and ease of use after setup.

If you are setting up a wired controller setup for the first time, we recommend this option.

<img src="../Images/ControllerSetup-ESP32-S3.jpg" height="350"> (picture of full ESP32-S3 setup)

Note that ESP32 and ESP32-S3 are different controllers made from the same company (Espressif).
 - ESP32 (aka ESP32-WROOM) is used for the wireless controller setup.
 - ESP32-S3 is used for this wired setup.

While the ESP32-S3 supports Bluetooth, it only supports Bluetooth LE. It does not support Bluetooth Classic as required by the Nintendo Switch. The reason why we chose it is because it has two USB ports - one goes to the Switch, the other is a built-in UART. Thus eliminating the need to manually wire up a UART as required by the Arduino/Teensy setups.

## Hardware Setup:

**Required Hardware (Full List):**
1. A regular [Nintendo Switch](../README.md#video-capture-card-the-computers-eyes) and its accessories (dock, power cable, HDMI cable). (You cannot use a Switch Lite.)
2. A [computer](../README.md#the-computer-the-player) running x64 Windows. (or another OS if you are able to set it up.)
3. A [video capture card](../README.md#video-capture-card-the-computers-eyes).
4. An ESP32-S3 microcontroller.
5. Two USB-C cables. One connects the ESP32-S3 to the computer while the other connects it to the Switch.

#1-3 are part of the initial setup so you should have all of these already.

**Estimated Total Cost (USD):** (not including computer and Nintendo Switch)
- **Single Setup:** $25 - $35
- **Bulk Purchase:** ~$18 per setup

(picture of full ESP32-S3 setup with annotations)

**Important:** There are many variants of the ESP32 microcontroller. Only the ESP32-3 will work. So you must get that specific model. (e.g. Don't get the ESP32-WROOM, or ESP32-S2-WROOM, or ESP32-C2, etc.)


### Recommended Purchase Links:

**Capture Card:** [See previous section.](../README.md#video-capture-card-the-computers-eyes)

**ESP32-S3 Microcontroller:**

| **Quantity** | **Price / Unit** | **Shopping Link** |
| --- | --- | --- |
| 1 (no pins) | $9 / unit | https://www.amazon.com/gp/product/B0BVVGNBB3/ |
| 3 (no pins) | $6 / unit | https://www.amazon.com/gp/product/B0C9H7Y66W/ |

Even though these are all made in China, AliExpress isn't much cheaper. (~$6/unit in bulk)

**Important:**

The ESP32-S3 exists in two variants: 1 USB or 2 USBs. You must get a model that has 2 USB ports on it. 

We recommend getting ones without pins since you don't need them. Having the pins is a liability for accidentally shorting out and damaging the board.

<img src="../Images/ControllerSetup-ESP32-S3-Board.jpg" height="300">

**USB Cables:**
- USB-C -> USB-A: https://www.amazon.com/Charging-Durable-Station-Compatible-Samsung/dp/B08LL1SVZD
- USB-C -> USB-C: https://www.amazon.com/3-Pack-Charging-Braided-iPhone-Samsung/dp/B0D222QDF1

Pick the ones that are appropriate for your computer and Switch dock.

### Hardware Assembly:

Unlike the ESP32 wireless setup, there are two USB ports. They are not interchangable so you must connect the right ones to the right places.

1. Turn your ESP32-S3 over to the back side. Next to each of the two USB ports, you will see the labels "USB" and "COM". These identify which port is which.
2. Connect the "USB" side to your Nintendo Switch.
3. Connect the "COM" side to your computer.

<img src="../Images/ControllerSetup-ESP32-S3-Backside.jpg">

And that's it! One extra cable compared to the ESP32 wireless setup, but still much simpler than the Arduino/Teensy setups. The "COM" port is the built-in UART that eliminates the need to manually wire up an external UART.


## Software Setup

### Step 0: Getting Ready

Make sure you have everything else setup so that it looks like this:

<img src="../Images/GeneralSetup-CC.png">

If not, you should go back to the [general setup guide](../README.md) and start over.

### Step 1: Flash the firmware to the ESP32.

**Flash the ESP32:**

1. Download the Espressif flash utility: https://dl.espressif.com/public/flash_download_tool.zip
2. Unzip, then run `flash_download_tool_3.9.7.exe` (version number may vary)
3. When you see the following menu, select "ESP32-S3" and "Develop". Then hit OK.

(insert image of flash utility)

4. You will then be prompted with this complicated window. Fill everything as follows:
   - Check the box for the first entry.
   - For the first entry, click on the `...` and browse for `PABotBase-ESP32-S3-2025032100.bin` in the serial programs download folder. (version number may vary)
   - The right-most box should be a zero.
   - At the bottom right corner, select the COM port of your ESP32-S3.
   - Change "BAUD" to 460800.

(insert image of flash utility with correct options selected)

5. Click Start and it should flash the PABotBase firmware to your ESP32-S3.

If everything worked correctly, you should see a green progress bar like this. If you see that it gets stuck printing out `...` and never makes progress, see [troubleshooting](#unable-to-flash-the-esp32-s3-stuck-on-).

(insert image of successful flash)

6. Reboot your ESP32-S3. You can do this either by:
   - Pressing either the `EN` or `RESET` button on the ESP32-S3.
   - Unplugging both USB cables and plugging them back in.

At this point, your final setup should look like this:

(insert image of CC window showing the connected status)

### Step 2: Connect the ESP32-S3 to the Computer Control program

1. At the top for the "Controller" option, click the dropdown and select `Serial: PABotBase` (should be on this since this is the default)
2. In the next dropdown, select your serial device. On Windows it will be something like `COM3`.

If you don't see the device in the dropdown, you probably need to refresh it (especially if you kept the program open since Step 0). You can refresh the list by clicking "Reset Ctrl".

If everything worked correctly, it will look like this:

(insert image of CC program with ESP32-S3 connected)

If you see the following instead, then you actually connected to our wireless controller setup instead (ESP32-WROOM). (We love your enthusiasm for having both setups!)

<img src="../Images/ControllerSetup-AVR8-ESP32.png">

Both the wired and wireless setups use serial ports. The program can distinguish them when it connects to it.

### Step 4: Test the connection

You can control your Switch from the keyboard. Click on the video display to activate the keyboard controls. Then try pressing some buttons. You can view the keyboard -> controller mapping by clicking on the "keyboard layout" at the bottom left corner of the program.

We recommend familiarizing yourself with the keyboard controls as this is the preferred way to control your Switch while setting up to run a program. In effect you can play your Switch from your computer. While it's not as nice as using a native controller, it is good enough to easily setup programs - especially if you're doing this remotely where you do not have physical access to the Switch.

The default layout is the standard WASD setup for FPS games on the most common QWERTY keyboard layout. If you don't like it or you have a different keyboard layout, you can change the key mappings in the "Framework Settings" panel at the top of the program list to the left.

(update image with ESP32-S3 instead)
<img src="../Images/ControllerSetup-AVR8-Controls.png">

### Step 5: You are done!

If keyboard commands are working (along with video and audio), you are done!

Try clicking on other programs on the sidebar. You will find that all of them are "virtual consoles" that will accept keyboard commands. At the top of every program is a link to the wiki that explains how to setup and use that program.

Continue on to [Finishing Up](../README.md#step-4-finishing-up)!





## Troubleshooting:

### Unable to flash the ESP32-S3. (stuck on `...`)

If you see that it gets stuck printing out `...` and never makes progress, try one of these:

**Solution 1:**
  1. Start the flash such that it is printing out `...`
  2. Press and hold the `BOOT` button on the ESP32-S3.
  3. Release the `BOOT` button when you see the green bar make progress.
     
**Solution 2:**
  1. Start the flash such that it is printing out `...`
  2. Press and hold the `RESET` (EN) button.
  3. Press and hold the `BOOT` button.
  4. Release the `RESET` (EN) button.
  5. Release the `BOOT` button.

If neither solution works:
 - Try a different USB port.
 - Try putting a USB2 hub between the computer and the ESP32-S3.

If nothing works, you are not alone! This is a common problem with ESP32 boards.
 - Further reading: https://www.reddit.com/r/esp32/comments/11awl5h/a_fatal_error_occurred_failed_to_connect_to_esp32/
 - Come to [our Discord](https://discord.gg/cQ4gWxN) for help.

### Unable to connect to the ESP32-S3.

If you are unable to connect to the ESP32 in step 42 it means the ESP32-S3 either isn't booting up properly, or it isn't properly flashed. You may also try disconnecting and reconnecting the ESP32-S3 device. If this still fails, review step 1 above and ensure that you flashed the firmware properly onto the device.



<hr>

**Credits:**
- Kuroneko/Mysticial
- jw
- kichithewolf

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)






