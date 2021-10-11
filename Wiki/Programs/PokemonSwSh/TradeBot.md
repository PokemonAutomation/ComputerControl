# Trade Bot

**Related Programs:**
- **Microcontroller:** [Trade Bot](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/PokemonSwSh/TradeBot.md)
- **Computer Control:** [Trade Bot](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonSwSh/TradeBot.md) (this program)

The microcontroller and computer-control versions of this program are functionally identical.


## Program Description

TradeBot is a coded version of [SurpriseTrade](SurpriseTrade.md). The main use case is for hosting giveaways.

The program can sustain a trade every ~103 seconds. Thus it takes almost an hour to process a box. 

This program is experimental and is more suited for high-demand and high-quantity giveaways. As with SurpriseTrade, this program will skip Pokémon if no trade happens. Thus there will be many untraded Pokémon. Likewise, you will need many Pokémon to sustain a giveaway that lasts for a long period of time unattended.

### Setup of Settings

1. Text Speed: Fast
2. Casual mode: Off
3. Nicknaming needs to be off. (in case of a trade evolution)
4. If you are trading online, make sure you have a strong internet connection.

> If you wish to trade online, be connected to the internet before you start the program. Thus you will need to be fast when starting the program or you will be disconnected.

### Instructions

1. Enter the menu and put the cursor over the "Pokémon" option.
2. Exit the menu with "B" to return to the overworld.
3. Check there is nothing in front of you that can be interacted with.
4. Backed yourself into a corner where you cannot travel down or right.
5. Your location should be safe from getting attacked by wild Pokémon.
6. Start the program in game or the [Change Grip/Order Menu](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Programs/NintendoSwitch/ChangeGripOrderMenu.md) depending on which option you choose.

### Box Setup

1. Place boxes of Pokémon to be traded consecutively.
   - The boxes do not need to be full. Empty slots are safely skipped, but you will leave the partner waiting for a long time before disconnecting them without trading anything.
2. You must be on the first box.
3. Do not have any untradable Pokémon in these boxes. (no fused Pokémon)

> It goes without saying that this is a very dangerous program. Don’t run this program unattended unless the game is completely free of Pokémon you want to keep.

### Default Program Settings

Once started, this program will trade the specified number of boxes consecutively starting from the current box.

When the program reaches the end of a box, it will pause for a longer period before moving the next box. This is to ensure that any errors from a preceding trade will have cleared out.


   > **Known Corner Cases:**
   > - If no trading partner is found, no trade happens and the current Pokémon is skipped.
   > - If the trade partner is too slow to pick a Pokémon or confirm the trade, the trade will be canceled.
   > - If the trade partner cancels at any time, the program should back out without issues.
   > - If a trade results in an evolution, the program will self-recover.*
   > - If a trade results in an evolution and a new move, the program should recover*.
   > - This program will tolerate the above errors even at the end of a box.
   > 
   > *In these cases, self-recovery will mean skipping the next trade.
   > 
   > **Untested Corner Cases:**
   > - If a box slot is empty, it should be safely skipped.
   > - If a trade results in a new Pokédex entry, the program should self-recover.
   > - Untradable Pokémon: fused, illegal, etc...
   > - You get disconnected from the internet while the program is running.


## Options

This program uses [**Tolerate System Update Menu (fast)**](FrameworkSettings.md#tolerate-system-update-menu-fast) to bypass the system update window.

Most of the options here are self-explanatory.

<img src="images/TradeBot-Settings.png">



<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)




