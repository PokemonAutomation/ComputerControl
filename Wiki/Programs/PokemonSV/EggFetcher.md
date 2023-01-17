# Egg Fetcher

**Related Programs:**
 - [Egg Fetcher](EggFetcher.md) (this program)
 - [Egg Hatcher](EggHatcher.md)
 - [Egg Autonomous](EggAutonomous.md)

## Program Description

Make sandwiches and collect eggs.

<img src="images/EggFetcher-0.png">

### Setup of Settings

1. Text Speed: Fast
2. Skip Move Learning: On

### Box Setup

1. Place consecutive empty boxes to host collected eggs. Set the current box as the first of those boxes.

### Instructions

1. You have picniced at least once to clear in-game picnic guide.
2. For best performance, use the default tablecloth on your picnic table. Other tablecloths may contain white patterns that will slow down the program detecting the white picnic hand cursor.
3. You have a party of two or more Pokémon that can produce eggs. Usually one Ditto and another Pokémon. Eggs collected will not fill empty spots in the party. They will be sent to the current box directly.
4. Making a sandwich gives 100 exp to each party Pokémon. Make sure when the program is running, none of your party Pokémon will evolve by sandwich exp. You can use the option **Max number of sandwiches to make** to control at most how many sandwiches will be made to avoid evolving.
5. You have unlocked Great Peanut Butter Sandwich recipe (recipe ID 17). The program will make the sandwich to gain Egg Power Lv 2. Without Egg Power, it will be very slow to produce eggs in the picnic basket. You don't need to unlock other sandwich recipes. The program can read recipe IDs and find the correct recipe to use.
6. To make the program more reliable reading recipe IDs, you need to buy enough ingredients of all kinds so that all your unlocked recipes are available for making sandwiches in a picnic. For example, in the image below, Recipe 1, 12, 20 and 84 are available while Recipe 80 is not available. Available recipes have solid images, while unavailable recipes have semi-transparent images. Make sure all your unlocked recipes have solid images. This helps the program read recipe IDs.

<img src="images/SandwichRecipes.png">

7. You have bought enough ingredients for making enough sandwiches set by **Max number of sandwiches to make**. Each Great Peanut Butter Sandwich costs one butter, one peanut butter, one banana and one pick. Any pick is fine: the program will always choose the first pick in the pick selection list. You can buy lots of silver picks for the cheap price.
8. Fly to Zero Gate flying spot (see image below). Stand on foot. Don't get on your ride. Don't turn your character around. You can turn camera around.

<img src="images/ZeroGate.png">

9. Start the program in game.

Note: Pokémon with large parts of bright yellow color (e.g. Skeledirge) may interfere with the current visual feedback method, with a small chance to cause errors to egg fetching detection. Avoid those Pokémon if possible. For example, if you would like to breed shiny Fuecoco line, don't bring Skeledirge. Bring Fuecoco.


### Notes on Egg mechanism

- If there is only one Pokémon in your party holding an item and that item is a Destiny Knot, all the item-free Pokémon can only pair with that Destiny Knot holder to generate eggs. So you can bring multiple native Pokémon to all pair with a single foreign 6IV Ditto that holds a Destiny Knot to generate Masuda-method eggs with good IVs.

- If more than one Pokémon holds Destiny Knot and the rest holds nothing, only the Pokémon with Destiny Knots will pair among themselves. So if you bring two Ditto with Destiny Knots and some other Pokémon without items, you will never get eggs as Ditto won't produce eggs with another Ditto.

For more investigation on Scarlet & Violet egg mechanism and how to optimize egg fetching, visit https://rotomlabs.net/article/breeding-scarlet-violet.


## Options

The options here are self-explanatory.


## Credits

- **Author:** Gin
- Wakaraina (for experimenting with egg mechanism)

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


