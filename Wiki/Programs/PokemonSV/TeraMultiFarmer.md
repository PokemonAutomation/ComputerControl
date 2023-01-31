# Tera Multi-Farmer

## Program Description

Auto-host a raid from one Switch while farming it with 1-3 more Switches. Thus this is a multi-Switch program that requires at least 2 Switches to run.

This program can be used to farm both items and Pokémon from a raid. By using pre-programmed moves, it can also be used to farm herbs from higher level raids.

Starting from version 0.30.x, you can auto-host the remaining raid slots online for others join. Thus this program is effectively a multi-Switch version of the [regular Auto Host](AutoHost.md):

 - When auto-hosting for other people (either locally or online), this program has full feature parity with the [regular Auto Host](AutoHost.md). This includes bans, join tracking, and kill switch.
- If you are self-farming with fewer than 4 Switches, you can throw it on live-hosting to share the remaining spots with others. For harder raids, this could make it faster if having other players help you win faster.
- For raids that are too difficult to auto-host with one player, you can now put multiple Switches on it with full move selection. Most raids are probably winnable with 2 carefully programmed hosts assuming all the joiners go idle.



<img src="images/TeraMultiFarmer-0.png">

### Setup of Settings

**The Host Switch:**

1. Text Speed: Fast
2. System time: Un-synced
3. Auto-save is off.
4. Airplane mode is disabled and you are offline.
5. You have done a raid at least once to clear in-game raid guide.
6. You must be facing an active Tera raid crystal facing south.
7. Your location should be safe from getting attacked by wild Pokémon.
8. You are in the overworld with all menus closed.
9. Save the game in this position. (standing on north side of crystal facing south)

\*After completing a raid, your character will rotate to face south. Thus if you aren't already facing south, you will no longer be facing the crystal.

**The Raiding Switch(es):**

1. Text Speed: Fast
2. Airplane mode is disabled and you are offline.
3. You have done a raid at least once to clear in-game raid guide.
4. You are in a place where you can access the Poké Portal.
5. Your location should be safe from getting attacked by wild Pokémon.
6. You are in the overworld with all menus closed.

### Instructions:

Once you have set up your Switches as above, just start the program.

The hosting Switch will run an auto-hosting routine and the raiding Switches will join and farm it.


## Global Options

### Host Switch:

This selects which Switch is the hosting Switch. Can be any of the 4 Switches and must be one that exists. (Can't choose Switch 3 if you only have 2 enabled.)

### Max Wins:

Stop the program after this many wins.

### Mode:

- Farm by yourself. Use only the Switches controlled by the program. Do not allow anyone else to join.
- Host remaining slots locally.
- Host remaining slots online.

Hosting out the remaining slots is done using Discord notifications. It is not recommended to stream the video because the program expects your Switches to be the first entries in the lobby. Allowing others to see the stream will allow them to get in front of your own Switches.

### Auto-Hosting Options

See [Auto-Host Options](AutoHostOptions.md).

This entire section is only available if the mode is set to host the remaining slots.



## Per-Switch Options

These options can be customized on a per-Switch basis.

### Game Language

This is used by the raiding Switches for ball selection. Must be set properly on raiding Switches that are choosing to catch the Pokémon.

### Catch the Pokémon:

Check this if you want the Switch to catch the Pokémon. Only relevant to raiding Switches.

### Ball Select:

If the raiding Switch is set to catch the Pokémon, this is the ball to use.

### Tera Battle Options

See [Tera Battle Options](TeraBattleOptions.md).






## Credits

- **Author:** Kuroneko/Mysticial

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)






