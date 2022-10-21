# Computer-Control Programs - Software Tutorial

This the guide for setting up serial programs on Windows and macOS. If you are here, your basic hardware setup should be fully working. So now you are ready to move up to serial connectivity and video capture!

Setting up serial connection and video capture is the same regardless of what device you have. Therefore all the device-specific tutorials will merge here.

***Do not continue if you have not completed the [Microcontroller tutorial](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Software/README.md).***

***Do NOT skip the Microcontroller tutorial even if you have no intention to run Microcontroller programs. The Microcontroller tutorial provides basic information needed for both Microcontroller and Computer-Control programs.***

## Step 0: Make sure you are ready.

1. Have you completed the [Microcontroller tutorial](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Software/README.md)?
2. Do you have TurboA working via the Microcontroller programs?
3. Do you know what a .hex file is?
4. Do you know how to flash your device?
5. For Windows users, do you know what WinAVR is?
6. For Windows users, have you ever heard of one of these programs: QMK, TeensyLoader, or FLIP?
7. Do you know what the 5-second flash looks like on your device?

**If you answered NO to any of these questions, *STOP RIGHT NOW***. Disconnect everything from your device and go back to the [Microcontroller tutorial](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Software/README.md) and start over.

Most people who get stuck do so because they skipped the Microcontroller tutorial.

## Step 1: Acquire the Hardware

Make sure you have the serial hardware:
- [Serial Hardware](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Hardware/README.md)

## Step 2: Download the SerialPrograms package.

Download the latest version of our programs from [here](https://github.com/PokemonAutomation/ComputerControl/releases).

(The link should look like something like `PA-SerialPrograms-0.x.x-xxxxxxxx.zip`)

If you get a virus or malware warning, ignore it. These are known false positives. If you don't trust us, the [source code is here](https://github.com/PokemonAutomation/Arduino-Source/tree/main/SerialPrograms).

Once you have downloaded the package, unzip to somewhere you can access later. Do not put it on Microsoft OneDrive.

## Step 3: Flash PABotBase into your Device.

The root folder of the SerialPrograms package should have a set of .hex files for each of the different devices.

<img src="images/serial-programs-root.png" height="300">

Flash the appropriate one to your device.

***If you do not know how to do this, it means you skipped the [Microcontroller tutorial](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Software/README.md). STOP right now and go back to the Microcontroller tutorial.***

## Step 4: Setup the serial connection.

1. Turn on your Switch.
2. Connect your device (Teensy/Pro Micro/Arduino) to the Switch or its dock.
3. Connect the UART to your computer.

You may need to install the drivers for your UART:
- SiLabs CP210x:
   - For Windows: https://www.silabs.com/documents/public/software/CP210x_Windows_Drivers.zip
   - For macOS: https://www.silabs.com/documents/public/software/Mac_OSX_VCP_Driver.zip

**Install SiLabs CP210x on macOS:**
After unzip the downloaded .zip folder, run SiLabsUSBDriverDisk.dmg inside.
It will launch an installation GUI. Click through it to start the installation progress bar.
If you feel the progress bar is stuck, it may be macOS is preventing it from modifying the OS.
Go to System Preferences App and choose Security & Privacy.
You will see some text saying things like "macOS is preventing SiLabs CP210x drivers".
Click the lock icon in the lower left of the window, enter your password. Then click the button to allow the driver to modify the system.
After that, you will see the driver GUI shows installation success.


## Step 5: Setup the video capture.

1. Connect an HDMI cable from your Switch dock to your video capture card.
2. Connect your capture card to your computer.

Here is an example of a setup after steps 4 and 5.

<img src="/Wiki/Hardware/images/serial-setup.jpg" height="600">

## Step 6: Use SerialPrograms.

For macOS users, follow this [guide](../Developer/MacInstallationGuide.md) to build the program first.

For Windows users, simply run the `SerialPrograms-Windows.cmd` script.
<img src="images/serial-programs-main.png" height="600">

## Step 7: Setup SerialPrograms.

2. Under the "Serial Port" dropdown, select your serial device.
3. Under the "Camera" dropdown, select your video capture device.

If everything worked correctly, it should look like this.

<img src="images/serial-programs-setup.png">

**Interpreting the "Serial Port" Text**
1. Red "Not connected" - Cannot open port, or check wires, and drivers
2. Orange "Connecting" - Connected to port, but no response from device
   1. Check wires
3. "Incompatible Version" - Flash your device with the newest PABotBase hex

Output Window (Log):
1. Spamming of "RESET" messages with nothing else
   1. Check your wires
2. Spams of invalid length and CRC errors.
   1. Check your wires.
   2. Make sure you don't have a PLxxx UART Controller (If you do, you need to buy a CP21xx UART)


**Troubleshooting:**

If nothing shows up for Serial Port or Camera, then there is something wrong with your setup.

Common serial connection errors are:
- Switching the TX and RX connections.
- The serial port is in use by another program.
- The device is not running a compatible program.

Common video capture errors are:
- The capture card is in use by another program.
- The capture card is not receiving enough power over the USB connection.
- There are multiple capture cards connected to the same physical USB port on the computer (by means of a hub). (see [multiple capture cards](#multiple-switch-considerations))


## Step 8: Setup sound.

In the past, the program didn't support sound at all. So you needed to play it using Windows itself.
This has since changed. Not only do we support audio, some programs *require* sound to work correctly.

The sound options are below the Camera options. Most of these options are self-explanatory.
1. Select the Audio Input that comes from your capture card. If you don't know which one it is, try all of them.
2. Select the Audio Output for your speakers.
3. The slider is for playback volume. It has no effect on sound recognition. You can even mute it.

Audio output is completely optional. It is only for playback. Audio input is optional for programs that don't use sound recognition.

<img src="images/serial-programs-audio-1.png">

**Notes:**

- Some high-end capture cards (such as AVerMedia) do not have audio inputs. They use a proprietary system that fuses the audio channel with the video. Since we do not support this, you will need to run an audio cable from your Switch's headphone jack into your computer's line-in or microphone jacks.
- Due a quirk* with many cheap capture cards (including the ones we recommend), the left and right audio channels may be reversed. If this is the case for you, try the other "Interleaved Stereo" format.

\*This "quirk" causes both the OS and OBS to treat these capture cards as mono-channel audio. While we are able to recover the stereo output by separating the left/right audio channels, we can't always determine which is which - hence the reversed left/right channels.


## Step 9: Play around with the keyboard controls.

If you make it here, then both your serial connection and your video is working. Congrats! Now it's time to play with the program.

The default program is the Virtual Console. It simply displays the video from your Switch. If you click on the video, it will also activate keyboard controls so you can send button presses to the Switch. This allows you to play your Switch on your computer. Subsequently, this also allows full remote access to your Switches.

To view the keyboard/controller mapping, click on "Keyboard Layout" in the bottom left section of the program.

<img src="images/serial-programs-mapping.png" height="400">

The joystick mappings should be fairly standard for FPS and 3D adventure games. The remaining buttons are somewhat arbitrary and not necessarily intuitive.
As of this writing, there is no support for changing the key mapping.

The playability of this will depend drastically on the quality of your capture card. Some capture cards have very low video latency. Other cards may be too slow to play on the computer in real time. Regardless, even if it is slow, you can use the program for remote access to setup and run programs while you are away.

**Note:** Since `Shift` is mapped to the B button, you will need to disable Sticky Keys in the system. Alternatively, you can press `CTRL` for B. Some buttons have multiple keyboard keys that can be used to invoke it, but they are undocumented at this time.


## Step 10: Run a program.

Now that you know how to use the Virtual Console, you can try running some programs on the left panel. The first thing that you will notice is that every program is a virtual console!

Most of the current programs are identical to the native ones as they were directly ported from device code to computer. Only this time, you can configure and run them with a few clicks. There is no more need to flash the device every time you change programs!

You will notice that the programs are color-coded:
- **Black:** Not a real program.
- **Blue:** Program does not use video feedback. It can run on all devices (including Arduino Uno R3).
- **Red:** Program does not use video feedback. It cannot run on the Arduino Uno R3.
- **Green:** Program uses video feedback and requires video capture. It can run on all devices (including Arduino Uno R3).
- **Purple:** Program uses video feedback and requires video capture. It cannot run on the Arduino Uno R3.

## Notes

### WinAVR is not necessary.

For Windows users, since the SerialPrograms use a prebuilt PABotBase .hex binary, you don't actually need to install WinAVR to use it. So if you intend to use only the serial programs, you can skip installing the toolchain.

### The application can connect to the microcontroller programs.

This tutorial assumes that the device is running PABotBase. In reality the application will still recognize any of the [microcontroller programs](https://github.com/PokemonAutomation/Microcontroller) running on the device provided that the protocol versions are compatible.

PABotBase is the only program that will accept commands over serial, so you will not be able to control the other programs. However, logging from the program will appear in the output window.

### Programs do not always need to start in the grip menu.

Many of the programs in SerialPrograms are identical to the native ones that don't require serial. However, you don't always need to start them in the grip menu.
The purpose of the grip menu is to disconnect your manual controller so that the device can take over as the primary controller. But if you're using the keyboard to control your Switch, the device is likely already the primary controller. Therefore, some programs will work anyway if you can start them in the Switch Home menu or inside the game.

### Multiple Switch Considerations

If you have played with the Switch Viewer program, you will notice that it supports multiple Switches. This is a precursor to future releases that may have programs that utilize multiple Switches simultaneously.

However, we have found that setting up the hardware to handle multiple serial ports and capture cards can be tricky. Sometimes they work, sometimes they don't. And it's often difficult to troubleshoot. This is regardless of whether you are running multiple Switches under the same instance or if you are running multiple instances of one Switch each.

**Serial ports and Cameras can only be used at one place at a time.**

Both serial ports and cameras (capture cards) can only be used by one application at a time. Therefore you cannot view the same video capture from both OBS and SerialPrograms simultaneously. If you want to do this, use the OBS Virtual Camera.

The single-use limitation also applies within the same application. When viewing multiple Switch setups simultaneously, both the serial ports and cameras can only be used at one place at a time. If you try to use the same serial port on a second setup, it won't connect. If you try to use the same camera on a second setup, it won't display.

**Capture Cards don't always play well with USB hubs.**

Capture cards are very hit-and-miss when you try to put multiple of them on the same USB hub.

Some general observations:
1. Capture cards draw a lot of power. If you put them with other high-powered USB devices drawing power from the same source, the card may not function.
2. Capture cards use a lot of USB bandwidth. If you put multiple capture cards on the same USB hub, you may saturate the bandwidth on that hub.
3. For some unknown reason (even when both the above do not apply), it can be difficult to get multiple capture cards on the same physical USB port (by means of a hub) on the computer to work simultaneously. You may need to spread them out. Thus for a 4-Switch setup, your computer will need at least 4 USB ports - one for each capture card. But within each port, you can use a hub to connect *one* capture card and other devices as well. (such as the UART serial connections)


## Next Steps

None. You're done!

- [Program List](/Wiki/Programs/README.md)


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)
