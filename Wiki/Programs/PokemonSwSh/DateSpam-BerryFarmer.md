# Date Spam - Berry Farmer

**Related Programs:**
- [Date Spam - Berry Farmer](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonSwSh/DateSpam-BerryFarmer.md) (this program)
- [Date Spam - Berry Farmer 2](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonSwSh/DateSpam-BerryFarmer2.md)

## Program Description

BerryFarmer will farm berries from a tree. It requires activating the Y-Comm glitch.

**Switch 1:**
- **Wired Controller:** 15.3 seconds/fetch
- **ESP32 Wireless:** 15.8 seconds/fetch
- **sys-botbase 2.x:** 22.5 seconds/fetch
- **sys-botbase 3.0:** TBD

**Switch 2:**
- **Wired Controller:** 15.9 seconds/fetch

<img src="images/DateSpam-BerryFarmer-0.png">

### Setup of Settings

**Switch Settings:**
1. Screen size: Must be 100% within the Switch settings
2. [Switch 2: The profile you are using must be the 1st (left-most) profile.](/Wiki/Programs/NintendoSwitch/Switch2Notes.md#resetting-a-game-moves-the-cursor-to-the-1st-user-profile)
3. System Time: Unsynced

**Program Settings:**
1. Video Resolution: 720p or higher

**Game Settings:**
1. Text Speed: Fast
2. Auto-Save: Off
3. Y-Comm glitch must be active
   1. Verify glitch is active by checking for a "flash" when re-entering the game from the Home menu.

### Instructions

1. You must be standing in front of a berry tree.
2. Your location should be safe from getting attacked by wild Pokémon.
3. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.

   > **Stability Recommendation:** Stand behind the berry tree so that the tree is directly in front of (and blocking) your character. Sometimes, the program will miss a button press which causes the date-spamming to happen in the game instead of the Switch settings. This will cause the character to move downwards and away from the tree if you're not standing behind it.


## Options

This program does not have the ability to avoid the system update window. Should the window appear while the program is running, the program will enter a safe do-nothing loop within the Switch settings.

Most of the options here are self-explanatory.

<img src="images/DateSpam-BerryFarmer-Settings.png">


## Credits

- **Author:** Kuroneko/Mysticial
- **Optimized:** SakuraKim
- **Ported to CC:** Kuroneko/Mysticial


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


