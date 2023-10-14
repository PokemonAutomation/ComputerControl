# Shiny Hunt - Scatterbug

<!-- <img src="images/ShinyHunt-AreaZeroPlatform-0.png"> -->


## Program Description

This program will shiny hunt Pokémon around South Mesagoza Pokémon Center. Its main usage is to shiny hunt Scatterbug to collect all Vivillon forms. But it can also be used to collect shiny Pokémon that naturally spawn on land in South Mesagoza.

In particular, this program can be used to shiny hunt all of these Pokémon:

- Scatterbug
- Lechonk
- Tarountula
- Fletchling

And probably more.

This program works by making a sandwich to boost spawns and shiny rate, then repeatedly sending out your lead for Let's Go to kill everything in sight. It will reset the game if the sandwich expires with no desired Pokémon found. Because Let's Go auto-battle does not attack shinies, shinies will remain and (with fairly high probability) will wander close enough to your character to trigger an encounter. While the program cannot detect shinies in the overworld, it can hear them during an encounter.

Since the program cannot see shinies in the overworld, it will not immediately try to engage them when they spawn. So there is a chance that a shiny will be missed. But that's the cost of automating.

Like the encounter bots from Sword/Shield and BDSP, this encounter bot supports auto-catching by blindly throwing balls.

To shiny hunt Scatterbug for Vivillon form collection:
- In Sandwich Maker option:
  - Set Sandwich Recipe to be Sparkling + Title + Encounter and Bug.
  - Set the two Herb Mystica that can realize the above recipe, e.g. one Bitter and one Sweet.
- In Action Table option:
  - Set the first row to be: when encountering shiny Tarountula, the action is "Throw Balls".
  - Set the second row to be: when encountering shiny Scatterbug, the action is "Stop Program".

WARNING: if you interrupt the program or if the program stops due to an unknown program bug, you may want to reset the game to preserve the precious Herba Mystica! If you start the program again before resetting the game, the program will first save the game, permanently locking whatever sandwich ingredients you used in the last program run as consumed.

### Setup of Settings

1. Text Speed: Fast
2. Skip Move Learning: On
3. Give Nicknames: Off
4. Auto-Save: Off
5. After game version 2.0.1 (the DLC 1 update): Camera Support: On


### Instructions

1. Make sure your party is full.
2. Your lead Pokémon is not shiny. (Shiny will cause false positive detections.)
3. Your lead Pokémon is fast and capable of defeating everything without taking damage.
4. The size of your lead Pokémon is not huge (not as large as a Corviknight). The size of a Talonflame is fine.
5. All your party Pokémon won't produce evolve animation due to received XPs from battles.
6. You have plenty of potions for auto-healing.
7. You have plenty of balls for auto-catching.
8. Fly to South Mesagoza Pokémon Center.
9. You are on foot. (Not mounted on your ride.)
10. Start the program in the overworld with all menus closed.

**Additional Instructions for Making Sandwich **
1. You have picniced at least once to clear the picnic tutorial.
2. You have plenty of sandwich ingredients. (For any ingredient, you need at least 1 more than the required amount to successfully complete the sandwich.)
3. For best performances, select the default tablecloth for your picnic table. (Light-colored tablecloth may interfere with with video recognition.)

In sandwich mode, the Sparkling/Title/Encounter preset recipes have a built-in margin for fallen ingredients. It is an intended program feature to drop a few ingredients and still activate the correct sandwich powers.

## Options

<!-- <img src="images/ShinyHunt-AreaZeroPlatform-3.png"> -->

### Game Language:

This is the language of your game and is required to read the names of what you encounter. Thus this is also required for auto-catch to work.

### Sandwich Maker:

The program will make the selected sandwich on program start and on every sandwich reset to keep the desired sandwich power active.

- Sandwich Recipe: Select from a preset of recipes or custom sandwich mode. If running a generic recipe, select the type in the suboption. If running a paradox-specific recipe, select the target recipe in the suboption.
- Herba Mystica: Select the herba mystica pair to be used when running a generic recipe. Note that not every combination is possible.
- Custom Sandwich: If running on custom sandwich mode, use this table to select the ingredient(s) and condiment(s) to use for the sandwich.

For more information on the preset recipes, including what herba mystica combinations will fail or what ingredients are used for the paradox-specific recipes, please refer to [Generic Recipes](SandwichMaker.md) for details.

While the program will attempt to build any given custom recipe, it is not guaranteed to build it successfully. Please test that your custom sandwich is able to be built using the [Sandwich Maker](SandwichMaker.md) program first.

### Actions Table:

By default, the program will run from non-shinies and stop on shinies. Here you can specify an action for different encounter types by Pokémon name and shininess. This will let you auto-catch Pokémon in your desired ball type.

### Use 1st Move if Cannot Throw Ball:

If you can't throw a ball because the opponent is semi-invulnerable, use the 1st move instead. Therefore, your first move should be non-damaging to avoid killing the wild Pokémon.

### Video Capture:

Take a video of the encounter if the program detects a shiny.

### Go Home when Done:

If the programs stops for whatever intended reason (a shiny, or explicit stop condition), go to the Switch Home to freeze the game. This is useful for preserving remaining sandwich time.

### Auto-Heal %:

Auto-heal your lead if its HP drops below a certain point. This will obviously consume items from your inventory.


## Credits

- **Author:** Kuroneko/Mysticial, Gin
- Sandwich mode by Nymphea


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

