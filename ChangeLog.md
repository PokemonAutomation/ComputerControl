**Version 0.67.3 (private beta):**
- Discord integration no longer requires privileged intents. (credit Koi)
- FRLG battles will now tolerate battle start abilities. (credit dolphincurry)
- When you change from a pro controller to a 3rd party controller, you will get a warning.
- When you plug/unplug a serial device, the dropdowns will automatically update without needing to press Reset Ctrl.
- Improved reliability of SwSh Highlight RNG. (reported by Kingeun, credit fye)
- Improved reliability of FRLG fishing. (credit dolphincurry)

You will need to flash new firmware for this release. Apologies for the inconvenience.

You may have noticed that the wiki has been updated to mention that the AVR boards (Uno R3, Leonardo, Teensy, Pro Micro) are no longer supported. This is the next step in the deprecation of these older boards - pulling the guides and wikis for them. If you are still using these boards, you can still continue for now as we have yet to remove the CC-side driver code for PABotBase1. We are tentatively planning for a September timeframe for the complete removal of PABotBase1 (and thus support for the older AVR8 boards).
