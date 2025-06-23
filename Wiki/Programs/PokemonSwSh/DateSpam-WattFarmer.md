# Date Spam - Watt Farmer

## Program Description

WattFarmer will farm watts from a wishing piece beam. It requires activating the Y-Comm glitch.

**Switch 1:**
- **Wired Controller:** 9.0 seconds/fetch (~800k watts per hour at 2000/fetch)
- **ESP32 Wireless:** 9.5 seconds/fetch (~760k watts per hour at 2000/fetch)
- **sys-botbase 2.x:** TBD
- **sys-botbase 3.0:** TBD

**Switch 2:**
- **Wired Controller:** TBD

<img src="images/DateSpam-WattFarmer-0.png">

### Setup of Settings

**Switch Settings:**
1. Screen size: Must be 100% within the Switch settings
2. [Switch 2: The profile you are using must be the 1st (left-most) profile.](/Wiki/Programs/NintendoSwitch/Switch2Notes.md#resetting-a-game-moves-the-cursor-to-the-1st-user-profile)
3. System Time: Unsynced

**Program Settings:**
1. Video Resolution: 720p or higher

**Game Settings:**
1. Text Speed: Fast
2. Casual mode: Off
3. Y-Comm glitch must be active
   1. Verify glitch is active by checking for a "flash" when re-entering the game from the Home menu.
4. You must be offline.
5. Airplane mode must be off.

   > **Stability Recommendation:** Stand ***behind*** the den so that the beam is directly in front of your character. Sometimes, the program will miss a button press which causes the date-spamming to happen in the game instead of the Switch settings. This will cause the character to move downwards and away from the den if you're not standing behind it.

### Activating the Y-Comm glitch

1. Go to a secure indoor location in game like a Pokécenter and save your game.
2. Open Y-Comm and connect to Internet.
3. Select Link battle and attempt to start a singles link battle.
4. When the game backs you out of Y-Comm: Hold the Home Button to access quick settings.
5. Toggle airplane mode as soon as the text announcing a match was found appears, on and off again to disconnect from the internet.
6. Press the Home button to hide Quick Settings.
7. Click "B" through the warnings.
8. Click the home button and return to the Home menu.
9. Re-enter the game. If the screen "blinks", you know the glitch was done correctly.

### Instructions

1. You must be standing in front of a wishing piece den with watts collected.
2. Your location should be safe from getting attacked by wild Pokémon.
3. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.


## Options

This program does not have the ability to avoid the system update window. Should the window appear while the program is running, the program will enter a safe do-nothing loop within the Switch settings.

Most of the options here are self-explanatory.

<img src="images/DateSpam-WattFarmer-Settings.png">


## Credits

- **Author:** Kuroneko/Mysticial
- **Optimized:** SakuraKim
- **Ported to CC:** Kuroneko/Mysticial


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


