**Version 0.67.4 (public beta):**

Program Changes:
- New Program: FRLG Roaming RNG. (credit Astro)
- Added PLZA Stats Reset: Hoopa (credit ZHDreamer)
- Added PLZA Stats Reset: Marshadow (credit Nymphia)
- Discord integration no longer requires privileged intents. (credit Koi)
- FRLG battles will now tolerate battle start abilities. (credit dolphincurry)
- FRLG Item Cloning is now faster. (reported by Arc, credit dolphincurry)
- Improved reliability of Living Dex sorter. (reported by ChefBoyarjay , credit dolphincurry)
- Improved reliability of BDSP end battle detection. (reported by Qube340 and Patrick
- Fixed PLZA Box Sorter alpha sorting. (reported by Maxxetto, credit dolphincurry)
- Fixed language option missing from EV Trainer. (reported by Patrick, credit pifopi)
- Improved reliability of SwSh Highlight RNG. (reported by Kingeun, credit fye)
- Improved reliability of FRLG fishing. (credit dolphincurry)
- Improved reliability of FRLG shiny box detection. (reported by Maxxetto, credit dolphincurry)
- More FRLG RNG calibrations improvements/fixes. (credit Astro)
- ESP32-S3 and Pico (UART mode) will now default to "NS1: Wired Pro Controller" fresh out of boot.
- When you change from a pro controller to a 3rd party controller, you will get a warning.
- When you plug/unplug a serial device, the dropdowns will automatically update without needing to press Reset Ctrl.

Firmware Changes:
- Major rewrite of the ESP32 firmware to fix some long standing issues. It should now be as reliable as the Pico W for wireless.
- ESP32 will now reliably reconnect to the Switch 1.
- ESP32 no longer silently disconnects.
- Fixed an issue in both ESP32 and Pico where having two Switches in the grip menu when trying to pair can royally mess things up.

You will need to flash new firmware to use this release.
