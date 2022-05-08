# Shiny Hunt - Overworld

## Program Description

This program will shiny hunt random encounters (grass, cave). It supports both single and double encounters.

This program does not work in the Grand Underground.

<img src="images/ShinyHunt-Overworld-0.png">

Demo Video: https://cdn.discordapp.com/attachments/755635697737531544/911482282295058453/2021-11-19_22-56-40.mp4

### Setup of Settings

1. Screen size: Must be 100% within the Switch settings
2. Video Resolution: 1080p or higher in program settings
   > Shiny detection and text recognition is not reliable at low resolutions.
3. Text Speed: Fast

### Setup of Party
1. Your lead Pokémon must be able to run away. (faster or holding Smoke Ball)
2. Your lead Pokémon must not be shiny. (This may cause false positives if a capture card lags)
   > **Recommended for Performance**
   > - Your lead Pokémon does not have high happiness.
   > - Your lead Pokémon does not have an ability that activates upon entry to battle.
3. **If using Sweet Scent** See `Trigger Method` below for additional party setup to trigger encounters.


### Instructions

1. Stand in a spot where you can move left/right or up/down forever and not wander off.
2. Make sure you are safe from getting attacked by trainers.
3. Start the program in game. Make sure the device is the connected controller.


## Options


### Go Home when Done:

After finding a shiny, go to the Switch Home to idle. Turn this off for unattended streaming so that your viewers can see the shiny.


### Game Language:

If set to a language, the program will attempt to read the name of each Pokémon you encounter and log it.

If you are playing in an Asian language (Japanese, Korean, Chinese), set your video resolution to 1080p or higher. These languages are difficult to accurately read with text recognition at low resolutions.


### Trigger Method:

Pick the one that's most appropriate for your location:

- Move left/right. (no bias)
- Move left/right. (bias left)
- Move left/right. (bias right)
- Move up/down. (no bias)
- Move up/down. (bias up)
- Move up/down. (bias down)
- Sweet Scent.

The "bias" will make it travel in that direction a little bit more. So if you're standing against a wall that's unbounded on the other side, you'll want to bias in the direction of the wall to avoid drifting away from it. Lead your party with a Pokémon of the ability like Illuminate to increase the encounter rate.

Sweet Scent method will select one of your Pokémon in the party and use Sweet Scent to start the encounter. Sweet Scent method has the benefit of adding no friendship to your party, while the other trigger methods increase friendship to your party because of constant walking. It can also be used in the Great Marsh without the limitation on the number of steps. The encounter rate of Sweet Scent is slightly below or if not about the same as the best encounter rate achieved by the other walking methods.

To use Sweet Scent:

1. The menu cursor should be over the Pokémon option.
2. There must be a Pokémon in your party knowing the move Sweet Scent.
3. The move must be callable as the second menu item when you select the Pokémon in the Pokémon view, directly after "Check summary". In other words, to avoid any trouble, don't let the Sweet Scent Pokémon know other overworld-usable moves like Dig.
4. The Sweet Scent Pokémon can be put in any location of the party. But for best performance place it as the party lead.


### Move Duration:

Travel for this long before changing directions.

### Sweet Scent Pokémon Location:

In case Sweet Scent is selected as the trigger method, the location of the Pokémon in the party to use Sweet Scent.


## Advanced Settings:
These are advanced settings. You shouldn't need to touch these unless something isn't working and you're trying to debug it yourself.


### Exit Battle Timeout:

After running, wait this long to return to the overworld. The program will resume before this time if it detects that that the battle has ended.


## Credits

- **Author:** Kuroneko/Mysticial



<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)




