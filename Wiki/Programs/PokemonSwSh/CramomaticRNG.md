# Cram-o-matic RNG

## Program Description

This program will perform RNG manipulation to get rare balls from the Cram-o-matic.

<img src="images/CramomaticRNG-0.png">

### Setup of Settings

1. Screen size: Must be 100% within the Switch settings
2. Video Resolution: 1280 x 720 or higher in program settings
3. Text Speed: Fast

### Instructions

1. Your lead Pokémon must be a non-shiny Orbeetle.
2. Stand in front of the Cram-o-matic.
3. Open the bag and place the cursor over the Apricorns you want to use.
 > If you want Sport Balls you need to have a second type of Apricorn directly below the one your cursor is placed on.
4. Close your bag and place the cursor over the "Pokémon" option.
5. Close the menu.
6. Start the program in-game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.



## Options

### Iterations:

The amount of times the Cram-o-matic is used.

This should be less than the amount of your selected Apricorns divided by 4. 
If you want Sport Balls this should be less than the lower amount of the two used Apricorns divided by 2.

  > If this is not set correctly the program might start to use other items from your bag, destroying them in the process. 
  > It is recommended to only use one type of Apricorn at a time to avoid problems if you run out of the chosen color of Apricorns.


### NPCs:

The number of NPCs in the dojo.

This number includes Pokémon.
It does **NOT** include the Cram-o-matic, Rotom terminal, vending machines or the TV.


### Wanted Ball:

The type of Ball you want. 

The exact type for each Color can be found [here](https://www.serebii.net/swordshield/cram-o-matic.shtml).


## Advanced Settings:

These are advanced settings. You shouldn't need to touch these unless something isn't working and you're trying to debug it yourself.


### Max unknown advances:

After one iteration this many states will be checked to find the current rng state.


### Only bonus:

Only target rng states which lead to getting five balls instead of one.

This will significantly increase the average time needed per iteration and is not recommended for Apricorn, Safari or Sport Balls.


## Credits

- **Discovery/original code to calculate target:** Anubis
- **Author:** Fye


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)




