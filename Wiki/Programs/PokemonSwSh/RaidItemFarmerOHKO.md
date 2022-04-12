# Raid Item Farmer OHKO

## Program Description

Farm items from max raids that can be one-hit-KO'ed.

> This program requires at least 2 Switches each with serial connections.

Use Cases:
- Farm Exp Candies off of a Shedinja raid.
- Farm Dynite Ore off of a baby Crown Tundra or promo den.

This program is not restricted to raids that can be OHKO'ed. By adjusting the appropriate timings, it can be used to farm any raid that can be finished in one turn (one move per player). For example, 3-star Delibird can be one-turned using a team of Zacians for a faster method of farming Dynite Ore.

[Demo Video.mov](https://cdn.discordapp.com/attachments/755635697737531544/814164114305581106/Candy_Farmer.mov)

<img src="https://raw.githubusercontent.com/PokemonAutomation/SwSh-Arduino/master/Documentation/SerialPrograms/images/CandyFarmer.png" height="600">

### Setup of Settings

Setup for All Switches:
1. Casual mode: Off
2. There are no other Switches nearby that can produce stamps. (watch out for auto-hosts!)
3. Whoever attacks first must be able to one-hit-KO (OHKO) the Pokémon.

Switch Hosting the Raid:
1. The hosting Switch is the upper-left Switch.
2. The first move of the lead Pokémon must be faster than the raid Pokémon.
3. The first move of the lead Pokémon must OHKO the raid Pokémon.
4. You are standing in front of a den containing Shedinja or something that can be OHKO'ed.
5. There are no watts in the den.
6. You are either saved in this position, or softlocked using the backup save method.
7. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.

Switch(s) Raiding:
1. Setup safeguards
   * The menu cursor is over the Pokédex; in case it fails to join the raid
   * In settings, Send to Boxes is set to Automatic; in case it catches the Pokémon
   * The default Poké Ball is a low value ball; in case it tries to catch the Pokémon
2. You are in the overworld and safe from being attacked.
3. There is nothing in front of you that can be interacted with.
4. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.

   > Additional Recommendations:
   > - Avoid using any Pokémon that have activating abilities. This adds delay and may require adjusting the default timings.

### Instructions

1. Setup settings, safeguards, and program per prior instruction
2. Save all Switches per item #7, if hosting raid, and item #4, if raiding.
3. Navigate all Switches to the Change Grip/Order Menu
4. Start the program

### Default Program Settings

The default program settings are intended to clear a raid in one move. You can adjust the settings to allow to clear a raid in one turn (one move per Switch).


## Options

Most of the options are self-explanatory timings which we won't cover. The program already provides descriptions for them.

### Load Backup Save:

Set to false if the host is saved on the Pokémon that is to be farmed. If the host is softlocked (using the backup save method), set this to true.

See [AutoHost-Rolling](AutoHost-Rolling.md) for more details on backup softlocks.

### Raid Start to Attack Delay:

Increase this if you need to use Pokémon that have activating abilities. For example: Using Zacian against Delibird.

### Attack to Catch Delay:

Increase this if you are farming something that cannot be OHKO'ed, but can still be one-turned. For example: Using multiple Zacians against Delibird.

### Rollover Prevention:

This program does not touch the date, but requires that the host stay on the current date frame. Thus after 24 hours, the day will rollover and change the Pokémon that is being hosted. To prevent this, the hosting Switch will periodically touch the date at the specified interval.

Set this value to zero to disable the feature.


## Credits

- **Author:** Kuroneko/Mysticial


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)




