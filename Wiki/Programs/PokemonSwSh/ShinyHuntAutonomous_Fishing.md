# Shiny Hunt (Autonomous) - Fishing

## Program Description

This program will shiny hunt fishing encounters.

[Demo Video.mov](https://cdn.discordapp.com/attachments/755635697737531544/823709108150075412/2021-03-22_19-04-14.mp4)

<img src="https://github.com/PokemonAutomation/SwSh-Arduino/raw/master/Documentation/SerialPrograms/images/ShinyHuntAutonomous-Fishing.jpg" width="800">

Unlike the Shiny Hunt (Unattended) programs, the Autonomous programs require no calibration. This program needs a capture card to detect a shiny from its animation.

### Setup of Settings

1. Screen size: Must be 100% within the Switch settings
2. Video Resolution: 1280 x 720 or higher in program settings
   > Shiny detection is not reliable at low resolutions.
   > If playing in an Asian language, your video resolution need to be 1080p. Text recognition is more accurate at higher resolutions.
3. Test Speed: Fast
4. Casual mode: Off
5. System time: Un-synced

### Setup of Party
1. Your lead Pokémon must be able to run away. (faster or holding Smoke Ball)
2. Your lead Pokémon must not be shiny. (this will cause false positive detection)

   > **Recommended for Performance:**
   > - Have the Shiny Charm. This triples the chance to find a shiny.
   > - Your lead Pokémon does not have high happiness.
   > - Your lead Pokémon does not have an ability that activates upon entry to battle.
   > - Zoom in. The bigger exclamation icon is easier for the inference to detect.


### Instructions

1. Stand in front of a fishing spot.
2. Save.
3. Return to overworld (not inside the menu).
4. Start the program in the [Change Grip/Order Menu](https://github.com/PokemonAutomation/SwSh-Arduino/wiki/Appendix:-ChangeGripOrderMenu).

### Default Program Settings

* When a shiny is found, the program will save a video of the encounter.
* The program will keep track of encounter statistics.

***

### Options

This program uses [`TOLERATE_SYSTEM_UPDATE_MENU_FAST`](https://github.com/PokemonAutomation/SwSh-Arduino/wiki/Appendix:-GlobalSettings#tolerate-system-update-menu-fast) to bypass the system update window.

There is no option to search only for a square shiny. Nearly all shinies are square and only 15/65536 are star. Therefore it is infeasible to hunt for star shiny.


### Go Home when Done:

After finding a shiny, go to the Switch Home to idle. Turn this off for unattended streaming so that your viewers can see the shiny.


### Game Language:

If set to a language, the program will attempt to read the name of each Pokémon you encounter and log it.

If you are playing in an Asian language (Japanese, Korean, Chinese), set your video resolution to 1080p or higher. These languages are difficult to accurately read with text recognition at low resolutions.


### Time Rollback:

Every this many hours, rollback the time by this many hours. This keeps the time constant to prevent the weather from changing. It also allows you to target time-specific marks. Set this to zero to disable this feature.


## Advanced Settings:
These are advanced settings. You shouldn't need to touch these unless something isn't working and you're trying to debug it yourself.


### Exit Battle Timeout:

After running, wait this long to return to the overworld. The program will resume before this time if it detects that that the battle has ended.

### Fish Respawn Time:

Wait this long for the fishing spot to respawn.

***

### Video Feedback:

**This program requires video feedback.**
