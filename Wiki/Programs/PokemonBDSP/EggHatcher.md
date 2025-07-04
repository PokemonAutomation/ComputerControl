# Egg Hatcher

***Warning: Egg hatching on BDSP is currently unstable. Use at your own risk!***

## Program Description

Hatch eggs from your boxes. This is the counterpart to [EggFetcher](EggFetcher.md).

### Setup of Settings

**Switch Settings:**
1. Screen size: Must be 100% within the Switch settings
2. [Switch 2: The profile you are using must be the 1st (left-most) profile.](/Wiki/Programs/NintendoSwitch/Switch2Notes.md#resetting-a-game-moves-the-cursor-to-the-1st-user-profile)

**Program Settings:**
1. Video Resolution: 1080p or higher

**Game Settings:**
1. Text Speed: Fast
2. Nicknaming: Off
3. The menu cursor is over the Pokémon option.

### Party Setup

1. Your party must have exactly 1 Pokémon.
   1. The Pokémon in your party MUST be a flame body (or similar) Pokémon.

### Pokémon Box Setup

1. Place entire boxes filled with eggs consecutively.
   1. It is okay to have non-eggs mixed in with eggs.
   2. The only requirement is that first row of each box is occupied.

2. You must be on the first box of eggs.

### Required Parameters:
- **Boxes to Hatch**: You MUST set this to the # of boxes you wish to hatch. Otherwise, you either won't hatch all the eggs you want, or the program goes crazy if you run out of eggs.
- **Step Count**: You MUST set this to the correct step-count for the Pokémon you are hatching. If this is set too small, the program will fail.

The program will hatch eggs in batches of 5 (one column at a time). Once a box is complete, it moves to the next box. It will continue until it has hatched N boxes where N is specified by **"Boxes to Hatch"**.

### Run Instructions

1. You are on your bike and in high gear.
2. Stand in the following location.
3. Start the program.

<img src="images/EggHatcher-0.png">


## Options

### Go Home when Done:

After the program finishes, go to the Switch Home to idle.

### Boxes of Eggs to Hatch:

Hatch this many boxes of eggs.

### Egg Step-Count:

The number of steps needed to hatch the eggs. Select the species that will hatch from the Egg.


## Advanced Settings:

These are advanced settings. You shouldn't need to touch these unless something isn't working and you're trying to debug it yourself.

### Safety Time:

Additional time added to the spinning. If any shinies are hatched, they will eat into this safety buffer along with any other unexpected slowdowns. Hatching a shiny takes 2 seconds longer than a non-shiny.

If you see that the program is going into Y-COMM or there is less than 5 seconds of extra spinning after the last egg in the batch, please report this as a bug. As a temporary work-around, you can increase this number.

### Hatch Delay:

Total animation time for hatching 5 eggs when there are no shinies.


## Credits

- **Author:** Kuroneko/Mysticial



<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)







