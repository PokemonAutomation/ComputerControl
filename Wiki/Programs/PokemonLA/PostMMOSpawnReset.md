# Post-MMO Spawn Reset

## Program Description

Shiny hunt Pokémon by resetting spawns after MMO finishes.

When MMO happens, the usual spawns (including alpha spawns) around an MMO spawn point is suppressed.
When you are near such location when MMO finishes, save and reset the game, the usual spawns will then appear around you and
they are different with each reset, meaning you can get shiny this way.

This program will repeatedly resetting the game and stop when it hears a shiny.

This program can be used to shiny-hunt every Pokémon from the spawn points (including alpha spawn points) that overlap with MMO spawns.


<!-- <img src="images/ShinyHunt-FlagPin-0.png"> -->

<!-- Demo Video: https://cdn.discordapp.com/attachments/755635697737531544/952330044246749224/2022-03-12_16-14-49.mp4 -->


### Settings

1. Screen size: Must be 100% within the Switch settings
2. Video Resolution: 1080p or higher in program settings
3. Audio input is properly setup.
4. Text speed is fast.
5. Vertical and Horizontal camera controls are both ***Regular***. Do not set either one to inverted.
6. Camera sensititivy it at the default value of 3.
7. Auto-save is off.


### Instructions

1. Go to your desired spawn point location when MMO is about to finish.
2. Wait until MMO finishes and make sure no usual spawns around you, then save the game.
7. Start the program in the game.

<!-- <img src="images/ShinyHunt-FlagPin-1.png"> -->

When you start the program, it will start the cycle of resetting the game and listening to shiny sound. After entering the game,
it can be set to move around according to the program options to correct your location if you save the game far from the spawn point you
intend to hunt.

It is strongly recommended to watch the program for a few runs to make sure it can move into the shiny sound range of the intended
spawn location. The spawned pokemon may spawn randomly near the spawn point and move around in different directions in each reset.
Make sure the path the program goes covers the optimal range of all possible pokemon locations.

This program will stop when it hears a shiny *anywhere* along the path. So you will likely get some "unwanted" shinies from another nearby
spawn point before the one you want actually shines.

As of this time, there is no option to ignore shinies that you don't want.


## Options

In case the place you save the game is not close to the spawn point you intend to shiny-hunt, here are some options to move the character
a bit after entering the game.


### Camera Turn

How many ticks to turn the camera to point to the direction you want to move towards.
You can input a positive or negative number. Positive numbers mean turning the camera rightside and negative numbers mean turning the camera leftside.


### Move Forward

After turning the camera, how many ticks to move forward. The program will move towards the direction the camera is facing.


### Wait Time

How many ticks to wait for the shiny sound after movement.


### Shiny Detected Actions

This program detects shinies by listening for the shiny sound. You can configure what the program should do if it hears a shiny.

**Shiny Detected Action:**
- Ignore the shiny. Do not stop the program.
- Stop program. Align camera for a screenshot. Then go Home.
- Stop program. Align camera for a screenshot + video. Then go Home.

**Screenshot Delay:**

If the above is set to stop on a shiny, the program will align the camera and wait X time to potentially allow the shiny to come into view of the camera.
This has no functional affect on the program. Don't set this value too large as some Pokémon will run away from you.


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)
