# Egg Autonomous

*This program is still in development. It is not yet available to the public.*

## Program Description

A fully autonomous bot that uses visual feedback to fetch and hatch eggs. It will automatically detect and keep shinies and can also be configured to keep specific gender and IV spreads. It combines the functionalities of [Egg Fetcher](EggFetcher.md) and [Egg Hatcher](EggHatcher.md).

At every iteration, this program collects 30 eggs and then hatch them. It keeps the hatched Pokémon that meets the requirement in a box and releases the rest. It can reset the game if there is no Pokémon to keep in those 30 eggs, thereby saving the ingredients of the Egg Power Lv 2 Sandwich. It can run completely unattended for many days without intervention.

<img src="images/EggAuto-0.png">
<img src="images/EggAuto-1.png">
<img src="images/EggAuto-2.png">


### Setup of Settings

1. Text Speed: Fast
2. Give Nicknames: Off
3. In-game Auto Save: Off, if you want the program to reset the game to save sandwich ingredients.

### Box Setup

1. Prepare three boxes.
- 1.1. Left box: place a Flame Body Pokémon at first row and first column of the left box. This Pokémon will be used to hatch the eggs. Make sure the second box column from the left is empty. This column will be used to hold your fetcher party when the program is hatching eggs.
- 1.2. Middle box: leave it empty.
- 1.3. Right box: this is the box to hold Pokémon you would like to keep. Give it enough space.
2. Set the current box as the middle box.
3. All three boxes need to use the defaul wallpaper, Wallpaper 1.
4. If you want to select keep Pokémon with certain IV spreads, you need to unlock IV judge functionality and set the current box view to be judge view.

### Instructions

1. You have picniced at least once to clear in-game picnic guide.
2. You have a party of two or more Pokémon that can produce eggs. Usually one Ditto and another Pokémon. Eggs collected will not fill empty spots in the party. They will be sent to the current box directly.
3. Making a sandwich gives 100 exp to each party Pokémon. Make sure when the program is running, none of your party Pokémon will evolve by sandwich exp.
4. You have unlocked Great Peanut Butter Sandwich recipe (recipe ID 17). The program will make the sandwich to gain Egg Power Lv 2. Without Egg Power, it will be very slow to produce eggs in the picnic basket.
5. You have bought enough ingredients for making the chosen number of sandwiches. Each Great Peanut Butter Sandwich costs one butter, one peanut butter, one banana and one pick. Any pick is fine: the program will always choose the first pick in the pick selection list. You can buy lots of silver picks for the cheap price.
6. Fly to Zero Gate flying spot (see image below).
7. Start the program in game.

<img src="images/ZeroGate.png">

### Notes on Egg mechanism

- If there is only one Pokémon in your party holding an item and that item is a Destiny Knot, all the item-free Pokémon can only pair with that Destiny Knot holder to generate eggs. So you can bring multiple native Pokémon to all pair with a single foreign 6IV Ditto that holds a Destiny Knot to generate Masuda-method eggs with good IVs.

- If more than one Pokémon holds Destiny Knot and the rest holds nothing, only the Pokémon with Destiny Knots will pair among themselves. So if you bring two Ditto with Destiny Knots and some other Pokémon without items, you will never get eggs as Ditto won't produce eggs with another Ditto.

For more investigation on Scarlet & Violet egg mechanism and how to optimize egg fetching, visit https://rotomlabs.net/article/breeding-scarlet-violet.



## Options

### Go Home when Done:

After the program finishes, go to the Switch Home to idle.

### Max Sandwiches:

How many Great Peanut Butter Sandwiches you can make before running out of ingredients.

### Game Language:

The language you are playing in. This is required only if you are doing IV filtering via the [Actions Table](#actions-table).

### Max Keepers:

Stop the program once it has kept this many babies.

### Auto-Saving:

You can set it to automatically save the game to recover from crashes, save ingredients or allow eggs to be unhatched.

**No auto-saving**: No error/crash recovery. If you find no kept Pokémon after end of the program, you can reset the game to recover sandwich ingredients. But if you want to keep any Pokémon, you will need to save the game afterwards and all the used ingredients are not recoverable.

**Save before picnic and after keeping a baby**: Allows for error/crash recovery. The program will reset the game if no kept Pokémon after one fetching-hatching iteration to recover the sandwich ingredients. Ingredients are only permanently spent when the program saves the game after a baby is kept.

**Save before every batch**: Allows you to unhatch eggs. Ingredients permanently spent after every picnic as the program will save before hatching each batch of five eggs. Unhatching eggs can be useful for obtaining breeding parents by rehatching a perfect egg in a game with a different language.
To collect (unhatched) eggs with the desired stats, set this option to "Save before every batch".
Then set the Action Table below to "Stop Program" on the desired stats.
Once the program stops on the baby with the desired stats, you can manually reset the game and it will revert to an egg in your party.

### Actions Table:

This tables lets you specify the actions to perform on babies that meet a certain criteria.

By default, there is one action which is to keep all shinies. (deposit them into the right box)
But you can add more actions to keep babies of certain gender and IV spreads. This is useful if you are still selectively breeding for perfect parents.


## Credits

- **Author:** Gin

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


