**Version 0.67.2:**
- Major rewrite of the ESP32 firmware to fix some long standing issues. It should now (in theory) be as reliable as the Pico W for wireless.
- ESP32 will now reliably reconnect to the Switch 1.
- ESP32 no longer silently disconnects. (further testing needed to confirm)
- Fixed an issue in both ESP32 and Pico where having two Switches in the grip menu when trying to pair can royally mess things up.
- Added PLZA Stats Reset: Hoopa (credit ZHDreamer)
- Added PLZA Stats Reset: Marshadow (credit Nymphia)
- FRLG Item Cloning is now faster. (reported by Arc, credit dolphincurry)
- Improved reliability of BDSP end battle detection. (reported by Qube340 and Patrick)
- Fixed PLZA Box Sorter alpha sorting. (reported by Maxxetto, credit dolphincurry)
- Fixed language option missing from EV Trainer. (reported by Patrick, credit pifopi)
- Improved reliability of FRLG shiny box detection. (reported by Maxxetto, credit dolphincurry)
- More FRLG RNG calibrations improvements/fixes. (credit Astro)

If you have an ESP32 (not the ESP32-S3), please help us test the new firmware since it is a very large change.

ESP32 and Pico W will require new firmware for this version.
