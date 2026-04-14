**Version 0.63.1 (public beta):**
- [Added a macro guide for FRLG RNG manipulation!](https://pokemonautomation.github.io/Programs/PokemonFRLG/MacroRngManipulation.html) (credit dolphincurry)
- Added FRLG Pickup Farmer (beta). (credit theastrogoth)
- Added FRLG shiny hunt fishing (beta). (credit Butters)
- Added Snorlax to FRLG legendary reset. (credit kichi)
- Added FRLG EV farmer (beta). (credit theastrogoth)
- Prize Reset now supports multiple fetches. (credit kichi)
- Stability improvements to all FRLG programs. (credit kichi)
- Stability improvements to SV AutoStory. (credit jw)
- Stability improvements to material farmer. (reported by butters2492, credit jw)

A full RNG program for FRLG is in the works courtesy of theastrogoth. Until then, we have that guide for RNG macros!

--------

**Deprecation Notice for AVR8 controllers:**

Sometime in the next few months (exact timeline is TBD), we will be removing support for all the AVR8-based controllers:
- Arduino Uno R3
- Arduino Leonardo
- Teensy 2.0
- Teensy++ 2.0
- Pro Micro

If you are still using these controllers, you will eventually need to upgrade to the newer ones: ESP32, ESP32-S3, Pico W

For years, we've been warning of dropping support for the Uno R3. Now it is finally happening - along with all the old boards.


**Why are we doing this?**

Last year's push to support new controllers (ESP32, ESP32-S3, Pico W) has produced amazing results. So after evaluating our long-term goals as well as our expected developer availability, we have decided to discontinue support for the old AVR8 controllers.

Dropping the AVR8 controllers will:
- Free up developer time to focus on other things.
- Eliminate the suffering of TX/RX wiring issues!

If you're interested in a full technical rundown on why we are finally doing this now after years of putting it off, feel free to ask in #automation-chat.
