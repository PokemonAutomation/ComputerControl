# God Egg Duplication

***This program is currently not available to the public since we do not condone mass cloning of Pokémon via methods that require hacking. It is only available to developers for research purposes.***

## Program Description

Duplicate Pokémon using the God Egg/MissingNo.

> Keep in mind that the God Egg is considered a form of hacking since there is no known way to obtain it without someone having a hacked Switch.*


### Setup of Settings

**Game Settings:**
1. Text Speed: Fast
2. Casual mode: Off
3. The "Send to Boxes" option must be set to "Manual".
4. Your bike must be fully upgraded.
5. You must have the God Egg and a Ditto deposited at the Route 5 daycare center.

> Strongly Recommended:
> - Have the Oval Charm.
> - The Ditto and the God Egg should have different OTs.

### Setup of Party

1. Your party is full.
2. There are no fused Pokémon in your party.
   1. Fused Pokémon cannot be released and will permanently take a box slot

### Box Setup

- The entire 1st column of the current box must be empty.
- Your party has 6 throw-away Pokémon.
   - If you don't want to clone all 6 Pokémon in your party, you can set **"Party Round Robin"** to cycle through fewer Pokémon.

### Safety Recommendations:
- Don't leave any Pokémon you care about in the game. This program releases Pokémon and has been observed to fail in a way that saves the game.
- If you do need to leave Pokémon you care about, keep them out of the 1st column of any box.

### Instructions

1. Fly to Route 5.
2. Get on your bike.
3. Open the menu and move the cursor over the Town Map.
4. Press "B" to return to the overworld (not in the menu).
5. Check there is nothing in front of you that can be interacted with.
6. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.

> *If you are playing in Japanese or Italian, you need to [**"Egg Fetch Extra Line"**](PokemonSettings.md#egg-fetch-extra-line) or this program will not work.*

### Default Program Settings

The program will clone each Pokémon in your party. Then it repeats the process forever.

***

### Options

This program uses [**Tolerate System Update Menu (fast)**](/Wiki/Programs/NintendoSwitch/FrameworkSettings.md#tolerate-system-update-menu-fast) to bypass the system update window.

In addition to the main options below, there are more [global options](PokemonSettings.md) that can be configured if you encounter problems.

### Fetch Attempts:

Make this many attempts to fetch and duplicate a Pokémon.

### Party Round Robin:

Round-robin through this many party Pokémon.

Examples:
- If set to 1, it will only clone the 1st party member.
- If set to 2, it will alternate the 1st and 2nd party members.
- If set to N, it will the 1st N members in your party in a round-robin fashion.
This option doesn't increase the speed of the cloning. It merely gives you more variety.


## Credits

- **Original:** SakuraKim
- **Ported to CC:** Kuroneko/Mysticial


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

