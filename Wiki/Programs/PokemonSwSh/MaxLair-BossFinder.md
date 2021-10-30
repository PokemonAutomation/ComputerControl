# Max Lair: Boss Finder

[Max Lair Info](MaxLair.md)

**Related Programs:**
- [Max Lair: Standard](MaxLair-Standard.md)
- [Max Lair: Boss Finder](MaxLair-BossFinder.md) (this program)


## Program Description

This program looks for a specific boss. It runs adventures with random bosses until it reaches a specific stop condition.
It does not reset the game or try to preserve balls, thus the path is random every time.

The stop conditions can be specified on a per-boss basis:
- Always stop program. (use this if you're looking for this boss)
- Stop if shiny.

Since this program does not know the boss for each adventure, win rates will be lower than the other modes.

### Setup of Settings

1. Screen size: Must be 100% within the Switch settings
2. Video Resolution: 1920 x 1080 or higher in program settings.
3. Text Speed: Fast
4. Casual mode: Off

This must be done to all participating Switches.

### Instructions

1. Stand in front of the professor.
2. If the hosting mode is "Alone" or "Host Locally", all Switches need to be offline.
3. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.

This must be done on all participating Switches.

The program will talk to the professor and start the adventure. It will automatically detect the boss from the silhouette (if available).


## General Options

This program uses [**Tolerate System Update Menu (fast)**](/Wiki/Programs/NintendoSwitch/FrameworkSettings.md#tolerate-system-update-menu-fast) to bypass the system update window.

### Host Switch

When running multiple Switches, this selects which one will be the hosting Switch.


## Per-Switch Options

### Game Language

You must pick the language that matches the game language.

### Normal Ball

This is the ball that will be used to catch all non-boss Pokémon.


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



