# Switch Viewer

**Related Programs:**
- **Computer Control:** [Virtual Console](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/NintendoSwitch/VirtualConsole.md)
- **Computer Control:** [Switch Viewer](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/NintendoSwitch/SwitchViewer.md) (this program)


## Program Description

The Switch Viewer is a multiple Switch version of the [Virtual Console](VirtualConsole.md).

This program is useful for figuring out your serial-to-camera mappings when you have multiple Switches connected for a multi-Switch program.

<img src="images/SwitchViewer-0.png">

Note that running multiple Switches is resource-intensive due to the video output. You will need a fairly powerful computer to handle 4 Switches with video at once.

(The computer in the screenshot above is overkill. You definitely do not need a 16-core computer to run 4 Switches.)

## Instructions

If you know how to use the Virtual Console, this should be pretty self-explanatory.

To figure out your serial/camera mappings:
1. Randomly open all the video captures and serial ports.
2. Input commands into one of the videos and see which video actually responds.
3. If the wrong video responds, swap either the video or the serial connections.
4. Repeat steps 2 and 3 until everything is mapped correctly.

Things to keep in mind:
1. Each serial port and camera can only be opened in one place at a time. In order to swap two ports/videos, you will need to first deactivate one of them by setting it to `(none)`.
2. Depending on where a Switch is in (game or Switch settings), the Switch may not respond to commands if there is another controller attached as the primary. So we recommend disconnecting all other controllers either physically, or by navigating into the [grip menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md).

The program will automatically save your settings when you close it. So you don't have to repeat this every time you run the program.

## Tips:

You can refresh the list of serial ports and camera either by changing programs on the left panel, or by changing a serial port of camera selection. This lets you configure your hardware on-the-fly without the need to close and reopen SerialPrograms.exe.


## Credits

- **Author:** Kuroneko/Mysticial


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


