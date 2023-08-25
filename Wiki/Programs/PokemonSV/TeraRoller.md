# Tera Roller

## Program Description

This program will date-spam for Tera Raids, enter & run away from the raid and check the Pokédex to see if the Tera Raid Pokémon is shiny.

This program is a variation of [Tera Self Farmer](PokemonSV/TeraSelfFarmer.md), but tailored for the sole purpose of finding a shiny Tera Raid for hosting. While this program cannot be used to farm Pokémon nor items, it is much faster per roll and not subject to having to win the Tera Raid.

**Note: This program will not work on Pokémon not in the Pokédex.**

### How This Works: Post-Encounter Dex Refresh

After encountering a Pokémon, no matter how the battle ends (running away, fainting, etc.) the Recently Battled section of the Pokédex will show an updated information that is relevant to the specific individual Pokémon (most notably gender, form, and shininess) regardless of previous dex registration status. By using this mechanism it is possible to gain information about a Tera Raid from the Recently Battled section after running away. This means we can know if a Tera Raid Pokémon is shiny without having to spend time to capture it.

For more information on the history and research regarding this mechanism please refer to this [Summary by ジュナリ](https://note.com/junari000/n/nc04cc0d3e6cb) (external site, written in Japanese).

### Setup of Settings

1. Text Speed: Fast
2. System Time: Unsynced
3. Auto Save: Off

### Instructions

1. You have done a Tera Raid at least once to clear the in-game tutorial.
2. Check in the Pokédex (long press minus in the overworld) that the 5 Recently Battled (not Recently Caught) Pokémon are not shiny. If there is a shiny, battle random wild Pokémon until all 5 Recently Battled Pokémon are not shiny. It's also okay if you have unregistered Pokémon, just make sure to have cleared the Pokédex tutorial.
3. You must be facing an active Tera Raid crystal facing south, or be standing directly on top of a crystal spawn spot.*
4. The player character is in a safe location that is unlikely to be attacked by wild Pokémon.
5. To save time, your lead Pokémon should not shiny and does not have an Ability that might trigger when entering battle.
6. Start the program in game.

\* After leaving a Tera Raid, the player character will face south by default. This may cause newly spawned crystals to no longer be interactable by the player, if the player is not already facing south.

## Options

### Check Only the First Pokédex Page:

When this option is checked, only the first (left-most) Pokémon in the Recently Battled section will be checked for shininess. This reduces the time per roll but will overlook cases if the player encounters the same species of Pokémon within the list of the 5 Recently Battled encounters.

### Opponent Filter:

**Min/Max Stars:** Skip all raids that don't have a star count in this range.

*Additional filters for species & event den will be added in the future.*

## Credits

- **Concept & Research:** ジュナリ
- **Japanese Dev Server Coordinator:** はんぺん
- **Adopting Concept to CC:** Nymphea

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


