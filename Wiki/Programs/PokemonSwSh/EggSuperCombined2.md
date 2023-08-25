# Egg Super Combined 2

**Related Programs:**
- **Microcontroller:** [Egg Super-Combined 2](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/PokemonSwSh/EggSuperCombined2.md)
- **Computer Control:** [Egg Super-Combined 2](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonSwSh/EggSuperCombined2.md) (this program)

The microcontroller and computer-control versions of this program are functionally identical.


## Program Description

Run [MassRelease](MassRelease.md), then run [EggCombined2](EggCombined2.md).

***Do not use this program until you are familiar with EggCombined since this is literally the same thing, but with an extra mass-release step. Therefore it is even more difficult to use correctly and safely.***

EggSuperCombined2 is the most optimized of the egg programs in this package. When used properly, it can allow 24/7 hatching while requiring the user to only touch the Switch twice a day. Thus this program is most suitable for mass production of hatched shinies - especially multiple Switches where you want to minimize the amount of interaction required for each Switch.

   * As with EggCombined2, this program will sustain upwards ***1700 eggs/day*** (5120 step) when used properly.
   * The idea of EggSuperCombined is to automate away the mass-release that's needed between EggCombined runs. So between runs after removing the shinies, you no longer need to run and wait for MassRelease to finish through before starting the next batch of eggs. Thus, the "interrupt" time between runs is now on the order of a few minutes instead of an hour to release 20+ boxes.
   * So you hatch eggs overnight. When you wake up in the morning, spend only a few minutes to remove shinies and fix boxes. Then start EggSuperCombined before heading to work. This allows you to hatch eggs 24/7 while touching the Switch only 2 or 3 times a day.
   * Experienced users will be able to sustain 24/7 hatching using only this program. The size of the egg reservoir can be kept in check by modifying the **"Fetches per Batch"** parameter.

<img src="images/EggCombined2-0.png">

### Setup of Settings

1. Text Speed: Fast
2. Casual mode: Off
3. The "Send to Boxes" option must be set to "Automatic".
4. Nicknaming needs to be off.
5. Your bike must be fully upgraded.
6. The parents are already deposited at the Route 5 daycare center.
7. The menu icons are in their default locations.
   1. The Town Map must be in the 2nd row on the far left.
   2. The Pokémon option must be in the 1st row, 2nd from the left.

> *If you are playing in Japanese or Italian, you need to [**"Egg Fetch Extra Line"**](PokemonSettings.md#egg-fetch-extra-line) or this program will not work.*

### Party Setup

1. Your party must have exactly 1 Pokémon.
   1. The Pokémon in your party MUST be a flame body (or similar) Pokémon.

### Pokémon Box Setup

1. The next N boxes can contain anything. They will be skipped.
2. Place entire boxes filled with eggs consecutively
   > It is okay to have non-eggs mixed in with eggs, But all boxes that you intend to hatch must be completely filled.
3. You must be on the first box of Pokémon to be released.
4. All the eggs that you are hatching MUST hatch at the same time and at the specified # of steps. Eggs are not allowed to hatch early
   > *Do not use this program on partially hatched eggs. Even a single early hatching egg can break the program.*

> **Failure Cases:**
> * It is safe to run out of box space. If the egg-fetching wraps around and occupies the current column, the program will fail safely by "re-hatching" the same party over and over again until it's done.
> * It is NOT safe to hatch an incomplete column due to running out of eggs. This will lead to an incomplete party being loaded which will swallow up newly fetched eggs. These eggs will not hatch at the correct time which will completely break the program.
> * It is NOT safe for eggs to hatch early. If an egg hatches during a fetch attempt, it can put the program into an unexpected state.


**Example Box Layout:**
```
Box  1: empty
Box  2: empty
Box  3: 30 breedjects 
Box  4: 30 breedjects
Box  5: 30 breedjects
Box  6: 15 breedjects
Box  7: your regular Pokémon
Box  8: 30 eggs
Box  9: 30 eggs
Box 10: 30 eggs
Box 11: 25 eggs
Box 12: empty
Box 13: empty
......
Box 32: empty
```
If using the above box layout; configure EggSuperCombined with these settings:
```
Boxes to Release    =   3
Boxes to Skip       =   2
Boxes to Hatch      =   30
```
Starting with Box 3 as the current box, the program will:
1. Release 3 boxes: 3, 4, 5
2. Skip 2 boxes: 6, 7
3. Run EggCombined for 30 boxes: 8-32 (wrap-around) 1-5

### Required Parameters:
- **Boxes to Release**: You MUST set this parameter correctly or you may release Pokémon you didn't intend to release!
- **Boxes to Skip**: You MUST set this parameter correctly or you may not hatch the correct boxes.
- **Boxes to Hatch**: You MUST set this to the # of boxes you wish to hatch. Otherwise, you either won't hatch all the eggs you want, or the program goes crazy if you run out of eggs.
- **Step Count**: You MUST set this to the correct step-count for the Pokémon you are hatching. If this is set too small or too large, the program will fail and may unintentionally start a trade. (see Precautions)

   > All recommendations, precautions, and usage tips for EggCombined apply to this program as well.

### Additional Recommendations:
- See [Maximizing Switch Stability](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/SwitchStability.md). The MassRelease portion of this program is sensitive to jitter.
- Don't leave any Pokémon you care about in the game. It goes without saying that mass-release is inherently dangerous to run unattended.
- Use a dedicated game with 32 empty boxes. If you're at the point where you're considering this program for optimized egg hatching, you might as well just speedrun a new game and shiny charm it with a living dex that you probably already have sitting in Pokémon Home.

### Run Instructions

1. Travel to Route 5.
2. Get on your bike.
3. Open the menu and place the cursor over the "Pokémon" option.
4. Hit "B" to return to the overworld (not in a menu).
5. Check that there is nothing in front of you that can be interacted with.
6. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.


## Options

This program uses [**Tolerate System Update Menu (fast)**](/Wiki/Programs/NintendoSwitch/FrameworkSettings.md#tolerate-system-update-menu-fast) to bypass the system update window.

In addition to the main options below, there are more [global options](PokemonSettings.md) that can be configured if you encounter problems.

<img src="images/EggSuperCombined2-Settings.png">

### # of Boxes to Release:

This is the number of boxes to release.

### # of Boxes to Skip:

This is the number of boxes to skip.

### Boxes of Eggs to Hatch:

Hatch this many boxes of eggs.

### Egg Step-Count:

The number of steps needed to hatch the eggs. Select the species that will hatch from the Egg.

### Fetches per Batch:

For each batch of eggs, attempt this many egg fetches. If this is a non-integer, the program will vary the # of fetches across batches so that they average out to the specified number.

By changing this number you can adjust the fetch rate of eggs. Thus with careful tuning, you can make egg fetching nearly the same speed as hatching.

Since there are 5 eggs per batch, you will need to set this value to more than 5.0 to match the hatch rate since some fetches will fail. The optimal value will depend on the step count and the compatibility of the parents.
Since this program is new, the exact fetch rates that lead to fetch/hatch equilibriums are not yet known. But they are believed to all be between 5.1 and 6.5.

### Rollover Prevention:

This is useful if your game is holding a den and you do not want an unintentional date-skip to destroy it.

Prevent the den from rolling over by periodically touching the date at this interval. Set this value to zero to disable the feature.


## Advanced Settings:
These are advanced settings. You shouldn't need to touch these unless something isn't working and you're trying to debug it yourself.

### Safety Time:

Additional time added to the spinning. If any shinies are hatched, they will eat into this safety buffer along with any other unexpected slowdowns. Hatching a shiny takes 2 seconds longer than a non-shiny.

If you see that the program is going into Y-COMM or there is less than 5 seconds of extra spinning after the last egg in the batch, please report this as a bug. As a temporary work-around, you can increase this number.

### Early Hatch Safety:

Eggs will not hatch early by more than this period.

### Hatch Delay:

Total animation time for hatching 5 eggs when there are no shinies.


## Credits

- **Author:** Kuroneko/Mysticial


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

