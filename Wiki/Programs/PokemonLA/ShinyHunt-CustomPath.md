# Shiny Hunt - Custom Path

**Related Programs:**
- [Shiny Hunt - Flag Pin](ShinyHunt-FlagPin.md)
- [Post MMO Spawn Reset](PostMMOSpawnReset.md)
- [Shiny Hunt - Custom Path](ShinyHunt-CustomPath.md) (this program)

## Program Description

This is a harder to use program that will shiny hunt Pokémon along a set path.

([Flag Pin](ShinyHunt-FlagPin.md) and [Post-MMO](PostMMOSpawnReset.md) cover nearly everything. But there are still a few holes left.

Some of the exceptions are covered by the specialized programs ([Crobat](AlphaCrobatHunter.md), [Froslass](AlphaFroslassHunter.md), [Gallade](AlphaGalladeHunter.md), etc...). But those are not exhaustive.

For example, Zorua:
1. Zorua cannot be hunted by Flag Pin because it's underground and requires turns.
2. Zorua cannot be hunted by Post-MMO because it's underground and away from any MMO spawns.
3. There are no specialized hunts for Zorua.

Thus the purpose of this program is cover some of the things that cannot be hunted with the existing programs.

[A collection of paths can be found here.](CustomPaths/)


### Settings

**Switch Settings:**
1. Screen size: Must be 100% within the Switch settings
2. [Switch 2: The profile you are using must be the 1st (left-most) profile.](/Wiki/Programs/NintendoSwitch/Switch2Notes.md#resetting-a-game-moves-the-cursor-to-the-1st-user-profile)

**Program Settings:**
1. Video Resolution: 1080p or higher
2. Audio input is properly setup.

**Game Settings:**
1. Text Speed: Fast
2. Auto-Save: Off
3. Vertical and Horizontal camera controls are both ***Regular***. Do not set either one to inverted.
4. Camera sensititivy it at the default value of 3.


### Instructions

1. You have unlocked Braviary.
2. You have unlocked all warp spots in the map you are hunting in. (unlocked both camps, the arena, and settlements - if applicable)
3. Program the path.
4. Select the desired start location in the options.
5. If the spawn you are hunting is dependent on the time of the day, set it now by resting at the tent.
6. Return to Jubilife Village and save the game in the below position.
7. Start the program in the game.

When you start the program, it will first travel to the desired start location and start running the path.



## Options


### Start Location

Pick a start location from which you will begin traveling to the flag.

Options include:
- All camps.
- All arenas.
- The Diamond and Pearl settlements.

Note that the Colbalt Coastlands arena has an alternate version where it moves to the northwest of the volcano. This allows you to reach the northern area of the map without getting stuck behind the lava.


### Custom Path Table

This is the table of instructions the program should run for the path. You can save/load the path to easily distribute it.

The available commands are:

**Change Mount**

Changes the mount.

**Move Forward**

Move forward for the specified number of ticks using one of several methods.

**Move in Direction**

Move the left joystick in the specified direction for the specified number of ticks.

This is the only way to make turns. Camera motion isn't supported since it's too unreliable and varies based on the user's camera sensitivity.

**Center Camera**

Presses ZL to center the camera in the direction you are facing. Use this after making a turn.

**Jump**

Jump off of Sneasler.

**Wait**

Do nothing for this direction.

**Start Listen**

Change the shiny detected action to the "Destination Shiny Action". Use this when are you near the destination.

**End Listen**

Change the shiny detected action to the "Enroute Shiny Action". Use this if you want to transition back to enroute.


### Reset Method

This option allows you to select how the program should reset once it reaches the flag.

Options:
- Soft Reset. (Safer option)
- Go back to village. (Faster option)

### Time of Day

Reset time of day if **Reset Method** is Soft Reset. Use this to only hunt Pokémon
at day or night, or to avoid visual inference errors on white snow at daytime.

### How Many Runs Before Resetting Time of Day
To avoid too much time spent on resetting time of day, reset only every several runs.

### Enroute/Destination Shiny Action

This program detects shinies by listening for the shiny sound. You can configure what the program should do if it hears a shiny.

There are two of these options - one for enroute, and one for the destination. Thus you can customize the behavior - such as ignoring shinies while enroute.

**Shiny Detected Action:**
- Ignore the shiny. Do not stop the program.
- Stop program. Align camera for a screenshot. Then go Home.
- Stop program. Align camera for a screenshot + video. Then go Home.

**Screenshot Delay:**

If the above is set to stop on a shiny, the program will align the camera and wait X time to potentially allow the shiny to come into view of the camera.
This has no functional affect on the program. Don't set this value too large as some Pokémon will run away from you.


## Credits

- **Author:** Gin
- Polished by Kuroneko/Mysticial.



<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)
