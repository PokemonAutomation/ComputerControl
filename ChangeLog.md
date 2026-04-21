**Version 0.63.7 (public beta):**
- Added FRLG RNG Helper. (credit Astro)
- Added FRLG Legendary Run-Away. (credit kichi)
- Added day/night filter to PLZA Bench Sit. (credit Butters)
- Various stability improvements to FRLG programs. (credit Astro)
- Fixed FriendDelete which broke on firmware update.
- Improved stability of PLA Outbreak Finder. (credit Boombaastical)
- Added support for PABotBase2 firmware protocol.
- ESP32, ESP32-S3, and Pico have been migrated to PABotBase2.
- Added support for non-W Raspberry Pi Picos. They will only support wired controllers.

**Built-in RNG Program for FRLG!**

The FRLG RNG program is finally out! For now it is "just" an organized collection of the existing macros with a UI for timing adjustments. We are exploring the idea of building a fully automated RNG program that will read stats, calculate seeds, and automatically calibrate your timings accordingly. But this is a big research area which we are not committed to.

**Work-in-Progress Programs:**

We currently have 3 more programs in beta testing that didn't make the cut for this release:
- FRLG: Lucky Egg Farming
- FRLG: Item Cloning
- Pokopia Cloud Island Reset

Hang tight for these. Maybe they'll make it into the next release. If you have private beta access, these are already available to use.

**PABotBase2:**

In our last release, we mentioned the deprecation of the AVR8 controllers. This release is step 1 in that process as we are releasing PABotBase2.

PABotBase2 is a complete rewrite/redesign of our firmware stack. It is not backwards compatible with the old stack (PABotBase1). Thus you will see two options in the controller dropdown, `PABotBase` and `PABotBase2`. Make sure you choose the right option for your installed firmware.
