# Day Skipper (JPN - 7.8k)

**Related Programs:**
- [Day Skipper (JPN)](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonSwSh/DaySkipperJPN.md)
- [Day Skipper (EU)](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonSwSh/DaySkipperEU.md)
- [Day Skipper (US)](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonSwSh/DaySkipperUS.md)
- [Day Skipper (JPN) - 7.8k](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonSwSh/DaySkipperJPN-7.8k.md) (this program)

There are different skippers for each date format. Use the one that matches yours or change your language/region to match the faster Japanese date skippers.


## Program Description

This is a faster JPN day skipper that runs at 7827 skips/hour.

> This skipper is less tolerant to errors compared to the other skippers. **Don't use this skipper unless your system is very stable or if you're just experimenting.**

This skipper works by looping through all 22,280 days from 2000/1/1 to 2060/12/31 then rewinding and starting over. The speed advantage over the other skippers is that it wastes a lot less time rewinding the year or rolling over the day of the month.

However, this slight increase in efficiency comes at a cost. The 7.8k skipper is less tolerant to errors. Unlike the other skippers in this package, the 7.8k skipper cannot always fully recover from every error.

While the 7.8k skipper can recover from minor errors, major errors will cause it to lose track of the date and thus run at a degraded speed of about 7570 skips/hour – which is slightly worse than the regular JPN date skipper. Likewise, once the program enters this "off-track" state, about 3.3% of the skips will be dropped which will cause the program fall significantly short of the target number of skips.

<img src="images/DaySkipperJPN-7.8k-0.png">

### Setup of Settings

1. System time: Un-synced
2. The language for your Switch must be set to Japanese (日本語).
3. Set the date to January 1st 2000.
3. Make sure the time of the day is not during the DST missing hour. (2 - 3AM)
4. The VS (Y-COMM) glitch must be active.

### Instructions

Most people use the following workflow:

1. Undock the Switch if it is docked.
2. Change the Switch language to Japanese.
3. Set the date to January 1st 2000.
4. Enter the game and go to a Pokémon center.
   1. The Isle of Armor dojo is not reliable!
5. Connect to the internet and start a link battle.
6. When someone is found, turn on airplane mode and keep it on.
7. Mash B to clear all the messages.
8. Confirm that the VS glitch is active by leaving and re-entering the game. The screen should flash when you re-enter the game.
9. Go into settings and date time.
10. Dock the Switch if desired.
11. Start the program.

   > Start the script anywhere in the Date/Time menu except the time zone menu. It will automatically find the right place.

   > If the game is a digital copy and the Switch is not the primary, you will not be able to turn on airplane mode for longer skips that take multiple hours. This is because the Switch will periodically check online to see if it's allowed to keep running the game. Airplane mode prevents this which causes the game to halt.
   > If this applies to you, either make the Switch the primary, or don't enable airplane mode. If you opt for the latter, you can expect the day skipper to make a lot more errors.

### Default Program Settings

When the program finishes skipping, it will continue to enter/exit the date change menu every 15 seconds without changing the date. This prevents the time from advancing naturally and potentially passing midnight which would result in an extra (unintended) day skip.

### Day Skipper Appendix:

It is strongly recommended to read each of these sections. These are common to all the day skippers.
- [Maximizing Switch Stability](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/SwitchStability.md)
- [Common Usage Errors](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/PokemonSwSh/DaySkippers.md#common-usage-errors#common-usage-errors)
- [How Many Skips are Remaining?](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/PokemonSwSh/DaySkippers.md#common-usage-errors#how-many-skips-are-remaining)
- [Errors and Auto-Corrections](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/PokemonSwSh/DaySkippers.md#common-usage-errors#errors-and-auto-corrections)


## Options

### Frame Skips: 
Skip this many frames. The actual number of skips performed may be less if any errors were made.

This can be as large as 4,294,967,295. But it will take 60+ years to skip that many frames.

### Start Date:

If you don't want to start on January 1st 2000, you can set your start date here.

### Auto-Recover Interval:

Perform an auto-recovery every this number of skips. This is the recovery routine that recovers from trapping errors. You shouldn't need to touch this value.


## Credits

- **Original:** SakuraKim
- **Ported to CC:** Kuroneko/Mysticial



<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


