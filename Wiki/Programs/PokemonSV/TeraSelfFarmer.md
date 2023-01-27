# Tera Self Farmer

## Program Description

This program will date-spam for tera raids and battle them by mashing A (the first move of your lead Pokémon).

This program is useful for farming items from easier raids. It cannot be used to beat hard raids.

This program can only detect shinies if it is set to catch the Pokémon. Thus it will skip all shinies in item-only mode.

(Starting from v0.29, the configuration options for this program has changed significantly.)

<img src="images/TeraSelfFarmer-0.png">

### Setup of Settings

1. Text Speed: Fast
2. System time: Un-synced
3. Give Nicknames: Off
4. Send to Boxes: Manual
5. Your party must be full.
6. The language in the option must match your in-game language. The program needs to read the ball names.
7. Auto save off if Shiny Hunt mode is active.

### Instructions

1. You have done a raid at least once to clear in-game raid guide.
2. You must be facing an active Tera raid crystal facing south, or standing directly on a crystal spawn spot.*
3. Your location should be safe from getting attacked by wild Pokémon.
4. Your lead Pokémon should be able to reliably beat raids by spamming its first move. Pick a move that is strong and has few types resistant to it.
5. Start the program in game.

\*After completing a raid, your character will rotate to face south. Thus if you aren't already facing south, the crystal spawns may no longer be in front of you.


## Options (Up to v0.28)

### Mode:

- Mode 1: LP only. Open the raid menu to get LP, but don't enter it.
- Mode 2: Items only. Don't catch anything.
- Mode 3: Catch everything using the specified ball.
- Mode 4: Shiny Hunt: Save before each raid and catch. Stop if shiny.

Mode 3 will look to see if what you caught is shiny and will send notifications.

Mode 4 will shiny hunt for a shiny Tera raid. If found, the program will stop. When you reset the game, you will be in front of the shiny raid. (assuming your date has not rolled over)


### Game Language:

The language of your game. This is needed to read the ball names to select the correct ball.


### Max Stars:

Skip raids with less than this many stars.


### Max Stars:

Skip raids with more than this many stars to save time since you're likely to lose. 5 star raids seem to be the limit of what can be beaten with this program.


### Try to Terastillize

Try to terastillize if available. Add 4s per try but greatly increase win rate.


### Max Catches

Stop program after catching this many Pokémon.


### Ball Select:

What ball to use to catch each raid Pokémon. The program will automatically stop if it cannot find this ball. (which will happen if you run out)


### Fix Clock on Catch:

Fix the time when catching so the caught date will be correct.



## Options (Starting from v0.29)

### Game Language:

The language of your game. This is needed to read the ball names to select the correct ball.


### Opponent Filter:

**Min/Max Stars:** Skip all raids that don't have a star count in this range.

By default it skips 5+ star raids since they usually have low win rates. But if you have a strong lead Pokémon, you can allow 5-star raids which may have herb rewards.


### Battle AI:

**Try to Terastillize:** Try to terastillize if available. Adds 4 seconds per try but can greatly increase win rate.

**Move Table:** Pre-program your Pokémon to use this sequence of moves.


### Catch on Win:

Check this box to catch the Pokémon when you win. Catching is required to check for shininess.

**Ball Select:** Catch the Pokémon using this ball.

**Fix Clock on Catch:** Fix the time when catching so the caught date will be correct.


### Stop Conditions:

**Max Catches:** Stop the program after catching this many Pokémon. Use this to avoid filling up all your boxes. If you are not catching, this parameter is ignored.

**Stop on Shiny:** Stop the program if the Pokémon you caught is shiny. Resetting the game will return you to the front of this (shiny) raid so it can be hosted again.

**Stop on Rate Items:** Stop the program if the item rewards contain at least this many rare (sparkly) items. Like for shinies, you can reset to re-host this raid. Set to zero to disable this and never stop for item rewards.



## Credits

- **Author:** Kuroneko/Mysticial

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


