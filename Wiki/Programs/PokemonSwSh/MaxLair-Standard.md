# Max Lair: Standard

[Max Lair Info](MaxLair.md)

**Related Programs:**
- [Max Lair: Standard](MaxLair-Standard.md) (this program)
- [Max Lair: Boss Finder](MaxLair-BossFinder.md)


## Program Description

This program runs adventures with a specific boss until a stop condition is reached. ([see below](#per-switch-options))

### Setup of Settings

1. Screen size: Must be 100% within the Switch settings
2. Video Resolution: 1920 x 1080 or higher in program settings.
3. Text Speed: Fast
4. Casual mode: Off
5. System time: Un-synced

This must be done to all participating Switches.

### Instructions

1. Stand in front of the professor.
2. Make sure you have at least one boss saved.
3. The host has not caught the boss that has been chosen.
4. If the hosting mode is "Alone" or "Host Locally", all Switches need to be offline.
5. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.

This must be done on all participating Switches.

The program will talk to the professor and start the adventure. It will automatically detect the boss from the silhouette (if available).


## General Options

This program uses [**Tolerate System Update Menu (fast)**](/Wiki/Programs/NintendoSwitch/FrameworkSettings.md#tolerate-system-update-menu-fast) to bypass the system update window.

### Host Switch

When running multiple Switches, this selects which one will be the hosting Switch. The host will be able to pick the boss. Everyone else will join the host.

### Boss Slot

The slot number of the boss.

- Slot 1: The 1st boss on the list. (the top one)
- Slot 2: The 2nd boss on the list.
- Slot 3: The 3rd boss on the list.


## Per-Switch Options

### Game Language

You must pick the language that matches the game language.

### Normal Ball

This is the ball that will be used to catch all non-boss Pokémon.

### Boss Ball

This is the ball that will be used to catch the boss.

### No Shiny Action, Non-Boss Shiny Action, Shiny Boss Action

At the end of each adventure, the result will be one of the following:
1. No shinies found.
2. One (or more) non-boss Pokémon is shiny.
3. The boss is shiny.

This option lets you tell the program what to do for each of these cases.

The possible actions are:
1. Stop Program. This stops the *entire* program - including for all Switches.
2. Continue Running. Take any shiny non-boss Pokémon along the way.
3. Reset the game.

Resetting the game will cost ore in the long run, but will recover the balls you used. If this Switch is the host, it will preserve the path that was just run.

***Setting this option to reset on the host Switch is equivalent to "Keep Path" from AutoMaxLair.***


## Hosting Options

### Mode

Pretty self-explanatory. The options are:
- **Alone:** Run by yourself using only Switches controlled by this program.
- **Host Locally:** Allow other local Switches to join.
- **Host Online:** Allow other people online to join.

When hosting, you may not actually be the host. You may join someone else's lobby with a compatible boss selection. In reality, there is no distinction between host and non-host.
The program is fully capable of playing as the non-primary player.

If multiple people (online or not) start the program at the same time with the same code and using compatible boss selections, they will join each other and play together.
This collaboration will continue from raid-to-raid until someone stops or drops out. Thus multiple people can work together using the same program to increase win rates for everyone.

### Raid Code:

See [Raid Code Entry](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/PokemonSwSh/RaidCode.md).

A raid code is required when running multiple Switches. This is because a code is needed to ensure that all the Switches will join the same lobby.



<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)



