# Post-MMO Spawn Reset

## Program Description

Shiny hunt Pokémon by resetting suppressed spawns after clearing MMO.

When MMO happens, the usual spawns (including alpha spawns) around an MMO spawn point is suppressed.
After you clear an MMO spawn point, stay there, save and reset the game, the usual spawns will then appear around you and
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

1. Enter a map with MMO.
2. Make sure the time of day is set correctly for your desired spawn to appear.
3. Go to your desired spawn point location.
4. Clear out the MMO spawns there. You can clear them either by despawning them (via catching, KOing, or scaring) or waiting for MMO to finish (rain or snow stops). Make sure the time of day and weather permit your desired spawn after you finish.
5. Stay at the location of the spawn point. Make sure your desired spawn is still suppressed. Save the game.
6. Start the program in the game.

<!-- <img src="images/ShinyHunt-FlagPin-1.png"> -->

When you start the program, it will start the cycle of resetting the game and listening to shiny sound. After entering the game,
the program can be set to move around according to the program options to correct your location if you save the game far from the desired spawn point.

It is strongly recommended to watch the program for a few runs to make sure it can move into the shiny sound range of the intended
spawn location. The spawned pokemon may appear randomly near the spawn point and move around in different directions in each reset.
Make sure the path the program goes on covers the optimal range of all possible pokemon locations.

This program will stop when it hears a shiny *anywhere* around you. So you will likely get some "unwanted" shinies from another nearby
spawn point before the one you want actually shines.

As of this time, there is no option to ignore shinies that you don't want.


### Caution

When you reset after the MMO is cleared, you can not use this save to go back to the state where the usual spawns don't appear.
So if you didn't set the correct time of the day or weather, you will not be able to hunt them on this save.

Fortunately, you can use the hidden backup save to revert the game back to a prior state.
Press DPAD UP, X and B at the same time at the game title screen to load the backup save.
This backup save is created whenever you enter a camp.
If your last visit to the camp is before the MMO spawns are cleared, then you can use this backup save to revert back the game in case your desired spawn does not appear after resetting the game due to wrong time of day or weather.
If your last visit is after the MMO spawns are cleared, then the backup save can not help you and you have to wait for another MMO to hunt what you want.


## Options

In case the place you save the game is not close to the spawn point you intend to shiny-hunt, here are some options to move the character
a bit after entering the game.

Make sure you set enough ticks in the options so that the program has enough time to wait for the game to finish loading and playing the shiny sound.


### Camera Turn

How many ticks to turn the camera to point to the direction you want to move towards.
You can input a positive or negative number. Positive numbers mean turning the camera rightside and negative numbers mean turning the camera leftside.


### Move Forward

After turning the camera, how many ticks to move forward. The program will move towards the direction the camera is facing.


### Wait Time

How many ticks to wait for the shiny sound after movement. Make sure you have set enough total time for the program to detect the shiny sound.


### Shiny Detected Actions

This program detects shinies by listening for the shiny sound.

**Shiny Detected Action:**
- Ignore the shiny. Do not stop the program.
- Stop program. Align camera for a screenshot. Then go Home.
- Stop program. Align camera for a screenshot + video. Then go Home.

**Screenshot Delay:**

If the above is set to stop on a shiny, the program will align the camera and wait X time to potentially allow the shiny to come into view of the camera.
This has no functional affect on the program. Don't set this value too large as some Pokémon will run away from you.


## Credits 
- So far the earliest source of the method is from [光之烙铁](https://tiebac.baidu.com/p/7759990346?pn=1)
- **Author:** Gin



<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)
