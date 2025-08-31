# Program List (Computer Control)

This is a list of all the computer-control programs. To run these programs, you need the [computer-control setup](/Wiki/SetupGuide/README.md).

**Notes:**
- Programs that require video feedback cannot run on the Switch Lite because it does not have HDMI output.
- Not every program can run on every controller. Please check the table for compatibility.
- Controllers marked as "Degraded" mean that the program will run, but performance and reliability may be severely degraded.

**Jump To:**
- [Nintendo Switch](#nintendo-switch)
- [Pokémon Let's Go Pikachu/Eevee](#pok%C3%A9mon-lets-go-pikachueevee-lgpe)
- [Pokémon Sword/Shield](#pokémon-swordshield)
- [Pokémon Brilliant Diamond/Shining Pearl](#pokémon-brilliant-diamondshining-pearl)
- [Pokémon Legends Arceus](#pokémon-legends-arceus)
- [Pokémon Scarlet/Violet](#pokémon-scarlet-and-violet)
- [Zelda: Tears of the Kingdom](#zelda-tears-of-the-kingdom)

**Controller Categories:**
| **Wired** | **Wireless** | **Other** |
| --- | --- | --- |
| - ESP32-S3<br>- Arduino Uno R3<br>- Arduino Leonardo<br>- Teensy 2.0<br>- Teensy++ 2.0<br>- Pro Micro<br>- sys-botbase 3 (sbb3) | - ESP32-WROOM | - sys-botbase 2.4 (sbb2) |

Read more about [Controller Performance Categories](/Wiki/ControllerList.md#https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/ControllerList.md#controller-performance-classes).


## Nintendo Switch

| **Program** | **Feedback** | **Controllers** |
| --- | --- | --- |
| [Framework Settings](NintendoSwitch/FrameworkSettings.md)         | --- | --- |
| [Virtual Console](NintendoSwitch/VirtualConsole.md)               | --- | All |
| [Switch Viewer](NintendoSwitch/SwitchViewer.md)                   | --- | All |
| [TurboA](NintendoSwitch/TurboA.md)                                |     | All |
| [Turbo Button](NintendoSwitch/TurboButton.md)                     |     | All |
| [Turbo Macro](NintendoSwitch/TurboMacro.md)                       |     | All |
| [Prevent Sleep](NintendoSwitch/PreventSleep.md)                   |     | All |
| [Friend Code Adder](NintendoSwitch/FriendCodeAdder.md)            |     | All (Degraded: sbb2) |
| [Friend Delete](NintendoSwitch/FriendDelete.md)                   |     | All |

## Pokémon Home

| **Program** | **Feedback** | **Controllers** |
| --- | --- | --- |
| [Page Swap](PokemonHome/PageSwap.md)                       |       | All |
| [Box Sorter](PokemonHome/BoxSorter.md)                     | Video | Wired, Wireless |

## Pokémon Let's Go Pikachu/Eevee (LGPE)

This game cannot be played with a Pro Controller and instead requires the use of joycons. Therefore, ESP32 wireless is the only supported setup since it is the only one that implements Joycons.

| **Program** | **Feedback** | **Controllers** |
| --- | --- | --- |
| Game Settings | --- | --- |
||
| **General:** |
| [Daily Item Farmer](PokemonLGPE/DailyItemFarmer.md)  | Video         | Wireless Only |
||
| **Shiny Hunting:** |
| [Alolan Trade](PokemonLGPE/AlolanTrade.md)           | Video         | Wireless Only |
| [Fossil Revival](PokemonLGPE/FossilRevival.md)       | Video         | Wireless Only |
| [Gift Reset](PokemonLGPE/GiftReset.md)               | Video         | Wireless Only |
| [Legendary Reset](PokemonLGPE/LegendaryReset.md)     | Video + Audio | Wireless Only |



## Pokémon Sword/Shield

| **Program** |  **Description** | **Feedback** | **Controllers** |
| --- | --- | --- | --- |
| [Game Settings](PokemonSwSh/PokemonSettings.md)        | --- | --- | --- |
||
| **QoL Macros:** |
| [Fast Code Entry (FCE)](PokemonSwSh/FastCodeEntry.md) |              |                  | All (Degraded: Wireless, sbb2) |
| [Friend Search Disconnect](PokemonSwSh/FriendSearchDisconnect.md) |  |                  | All |
||
| **General Programs:** |
| [Mass Release](PokemonSwSh/MassRelease.md) |                       |                  | All (Degraded: sbb2) |
| [Surprise Trade](PokemonSwSh/SurpriseTrade.md) |                   |                  | Wired, Wireless |
| [Trade Bot](PokemonSwSh/TradeBot.md) |                             |                  | Wired, Wireless |
| [Clothing Buyer](PokemonSwSh/ClothingBuyer.md) |                   |                  | All |
| [Autonomous Ball Thrower](PokemonSwSh/AutonomousBallThrower.md) |  | Video            | All |
| [Dex Rec Finder](PokemonSwSh/DexRecFinder.md) |                    | Video (Optional) | All (Degraded: sbb2) |
| [Box Reorder National Dex](PokemonSwSh/BoxReorderNationalDex.md) | | Video            | Wired, Wireless |
||
| **Date-Spam Farmers:** |
| [Date Spam: Watt Farmer](PokemonSwSh/DateSpam-WattFarmer.md) | Farm watts. To farm money, use watts to buy Luxury balls, then sell them. || All (Degraded: Wireless, sbb2) |
| [Date Spam: Berry Farmer](PokemonSwSh/DateSpam-BerryFarmer.md) | Farm berries.                                                           || All (Degraded: Wireless, sbb2) |
| [Date Spam: Berry Farmer 2](PokemonSwSh/DateSpam-BerryFarmer2.md) | Farm berries using audio/video feedback                              | Video + Audio | All (Degraded: sbb2) |
| [Date Spam: Loto Farmer](PokemonSwSh/DateSpam-LotoFarmer.md) |                          || All (Degraded: sbb2) |
| [Date Spam: Stow-On-Side Farmer](PokemonSwSh/DateSpam-StowOnSideFarmer.md) |            || All (Degraded: sbb2) |
| [Date Spam: Daily Highlight Farmer](PokemonSwSh/DateSpam-DailyHighlightFarmer.md) |     || All (Degraded: sbb2) |
| [Date Spam: Poké Jobs Farmer](PokemonSwSh/DateSpam-PokeJobsFarmer.md) |                 || All (Degraded: sbb2) |
||
| **Den Hunting:** |
| [Purple Beam Finder](PokemonSwSh/PurpleBeamFinder.md) |         | Video            | All |
| [Event Beam Finder](PokemonSwSh/EventBeamFinder.md) |           |                  | All |
| [Day Skipper (JPN)](PokemonSwSh/DaySkipperJPN.md) |             |                  | Wired, Wireless (Degraded: Wireless) |
| [Day Skipper (EU)](PokemonSwSh/DaySkipperEU.md) |               |                  | Wired, Wireless (Degraded: Wireless) |
| [Day Skipper (US)](PokemonSwSh/DaySkipperUS.md) |               |                  | Wired, Wireless (Degraded: Wireless) |
| [Day Skipper (JPN) - 7.8k](PokemonSwSh/DaySkipperJPN-7.8k.md) | |                  | Wired Only |
||
| **Hosting:** |
| [Den Roller](PokemonSwSh/DenRoller.md) |                    | Video (Optional) | All (Degraded: sbb2) |
| [Auto-Host Rolling](PokemonSwSh/AutoHost-Rolling.md) |      | Video (Optional) | All (Degraded: sbb2) |
| [Auto-Host Multi-Game](PokemonSwSh/AutoHost-MultiGame.md) | | Video (Optional) | All (Degraded: sbb2) |
||
| **Eggs:** |
| [Egg Fetcher 2](PokemonSwSh/EggFetcher2.md) |                              |       | All |
| [Egg Fetcher Multiple](PokemonSwSh/EggFetcherMultiple.md) |                |       | All |
| [Egg Hatcher](PokemonSwSh/EggHatcher.md) |                                 |       | All |
| [Egg Autonomous](PokemonSwSh/EggAutonomous.md) |                           | Video | All |
| [God Egg Item Duplication](PokemonSwSh/GodEggItemDuplication.md) |         |       | All (Degraded: sbb2) |
| [God Egg Duplication (developer only)](PokemonSwSh/GodEggDuplication.md) | |       | All (Degraded: sbb2) |
||
| **Non-Shiny Hunting:** |
| [Stats Reset](PokemonSwSh/StatsReset.md) |                   | Video | All |
| [Stats Reset - Calyrex](PokemonSwSh/StatsReset-Calyrex.md) | | Video | All |
| [Stats Reset - Moltres](PokemonSwSh/StatsReset-Moltres.md) | | Video | All |
| [Stats Reset - Regi](PokemonSwSh/StatsReset-Regi.md) |       | Video | All |
||
| **Shiny Hunting:** |
| [Multi-Game Fossil Revive](PokemonSwSh/MultiGameFossil.md) |                                      |                  | All (Degraded: sbb2) |
| [Curry Hunter](PokemonSwSh/CurryHunter.md) |                                                      | Video (Optional) | Wired, Wireless |
| [Shiny Hunt Autonomous - Regi](PokemonSwSh/ShinyHuntAutonomous-Regi.md) |                         | Video | All (Degraded: sbb2) |
| [Shiny Hunt Autonomous - Swords Of Justice](PokemonSwSh/ShinyHuntAutonomous-SwordsOfJustice.md) | | Video | All |
| [Shiny Hunt Autonomous - Strong Spawn](PokemonSwSh/ShinyHuntAutonomous-StrongSpawn.md) |          | Video | All |
| [Shiny Hunt Autonomous - Regigigas2](PokemonSwSh/ShinyHuntAutonomous-Regigigas2.md) |             | Video | All |
| [Shiny Hunt Autonomous - IoA Trade](PokemonSwSh/ShinyHuntAutonomous-IoATrade.md) |                | Video | All |
| [Shiny Hunt Autonomous - Berry Tree](PokemonSwSh/ShinyHuntAutonomous-BerryTree.md) |              | Video | All (Degraded: sbb2) |
| [Shiny Hunt Autonomous - Whistling](PokemonSwSh/ShinyHuntAutonomous-Whistling.md) |               | Video | All |
| [Shiny Hunt Autonomous - Fishing](PokemonSwSh/ShinyHuntAutonomous-Fishing.md) |                   | Video | All |
| [Shiny Hunt Autonomous - Overworld](PokemonSwSh/ShinyHuntAutonomous-Overworld.md) |               | Video | All |
||
| **RNG:** |
| [RNG Seed Finder](PokemonSwSh/SeedFinder.md) | Finds the current state to be used for manual RNG manipulation      | Video | All |
| [Cram-o-matic RNG](PokemonSwSh/CramomaticRNG.md) | Farm apriballs using RNG manip of Cram-o-matic                  | Video | All (Degraded: sbb2) |
||
| **Multi-Switch Programs:** |
| Synchronized Spinning |                                                    || All (Degraded: sbb2) |
| [Raid Item Farmer (OHKO)](PokemonSwSh/RaidItemFarmerOHKO.md)  |            || Wired, Wireless |
||
| [**Auto Max Lair 2.0:**](PokemonSwSh/MaxLair.md) |
| [Max Lair: Standard](PokemonSwSh/MaxLair-Standard.md) | Run Dynamax Adventures until a shiny Legendary is found.               | Video | All |
| [Max Lair: Strong Boss](PokemonSwSh/MaxLair-StrongBoss.md) | Run Dynamax Adventures and intelligently reset to keep paths with high win rates (for Legendaries that are hard to beat) | Video | All |
| [Max Lair: Boss Finder](PokemonSwSh/MaxLair-BossFinder.md) | Run Dynamax Adventures until you find the boss you want.          | Video | All |
||
| **Deprecated Programs:** |
||
| [Ball Thrower](PokemonSwSh/BallThrower.md) |                               |       | All |
| [Beam Reset](PokemonSwSh/BeamReset.md) |                                   |       | Wired, Wireless |
| [Egg Combined 2](PokemonSwSh/EggCombined2.md) |                            |       | Wired, Wireless |
| [Egg Super-Combined 2](PokemonSwSh/EggSuperCombined2.md) |                 |       | Wired, Wireless |
| [Shiny Hunt Unattended - Regi](PokemonSwSh/ShinyHuntUnattended-Regi.md) |                         |                  | Wired, Wireless |
| [Shiny Hunt Unattended - Swords Of Justice](PokemonSwSh/ShinyHuntUnattended-SwordsOfJustice.md) | |                  | Wired, Wireless |
| [Shiny Hunt Unattended - Strong Spawn](PokemonSwSh/ShinyHuntUnattended-StrongSpawn.md) |          |                  | Wired, Wireless |
| [Shiny Hunt Unattended - Regigigas2](PokemonSwSh/ShinyHuntUnattended-Regigigas2.md) |             |                  | Wired, Wireless |
| [Shiny Hunt Unattended - IoA Trade](PokemonSwSh/ShinyHuntUnattended-IoATrade.md) |                |                  | Wired, Wireless |


## Pokémon Brilliant Diamond/Shining Pearl

| **Program** | **Feedback** | **Controllers** |
| --- | --- | --- |
| Game Settings | --- | --- |
||
| **General:** |
| [Mass Release](PokemonBDSP/MassRelease.md)                            |       | All |
| [Autonomous Ball Thrower](PokemonBDSP/AutonomousBallThrower.md)       | Video | All |
||
| **Trading:** |
| [Self Box Trade](PokemonBDSP/SelfBoxTrade.md)                         | Video | All |
| [Self Touch Trade](PokemonBDSP/SelfTouchTrade.md)                     | Video | All |
||
| **Farming:** |
| [Money Farmer (Route 212)](PokemonBDSP/MoneyFarmerRoute212.md)        | Video | Wired, Wireless |
| [Money Farmer (Route 210)](PokemonBDSP/MoneyFarmerRoute210.md)        | Video | Wired, Wireless |
| [Double Battle Leveling](PokemonBDSP/DoublesLeveling.md)              | Video | All |
| [Amity Square Pick Up Farmer](PokemonBDSP/AmitySquarePickUpFarmer.md) |       | All |
| [Gift Berry Reset](PokemonBDSP/GiftBerryReset.md)                     | Video | All |
| [Poffin Cooker](PokemonBDSP/PoffinCooker.md)                          | Video | All (Degraded: sbb2) |
||
| **Shiny Hunting:** |
| [Starter Reset](PokemonBDSP/StarterReset.md)                          | Video | All |
| [Legendary Reset](PokemonBDSP/LegendaryReset.md)                      | Video | All |
| [Shiny Hunt - Overworld](PokemonBDSP/ShinyHunt-Overworld.md)          | Video | All |
| [Shiny Hunt - Fishing](PokemonBDSP/ShinyHunt-Fishing.md)              | Video | All |
| [Shiny Hunt - Shaymin](PokemonBDSP/ShinyHunt-Shaymin.md)              | Video | All |
||
| **Eggs:** |
| [Egg Fetcher](PokemonBDSP/EggFetcher.md)                              |       | All |
| [Egg Hatcher](PokemonBDSP/EggHatcher.md)                              |       | All |
| [Egg Autonomous](PokemonBDSP/EggAutonomous.md)                        | Video | All |
||
| **Glitches (v1.1.3):** |
| [Activate Menu Glitch (1.1.3)](PokemonBDSP/ActivateMenuGlitch-113.md)     | Video | Wired, Wireless |
| [Clone Items (Box Copy Method 2)](PokemonBDSP/CloneItemsBoxCopy2.md)      | Video | Wired, Wireless |
||
| **Glitches (v1.1.2):** |
| [Activate Menu Glitch (1.1.2)](PokemonBDSP/ActivateMenuGlitch-Poketch.md) | Video | Wired, Wireless |


## Pokémon Legends Arceus

| **Program** | **Feedback** | **Controllers** |
| --- | --- | --- |
| Game Settings | --- | --- |
||
| **General:** |
| [Braviary Height Glitch](PokemonLA/BraviaryHeightGlitch.md)           |               | All |
| [Distortion Waiter](PokemonLA/DistortionWaiter.md)                    | Video         | All |
| [Outbreak Finder](PokemonLA/OutbreakFinder.md)                        | Video         | All |
| [Clothing Buyer](PokemonLA/ClothingBuyer.md)                          |               | All |
| [Skip To Full Moon](PokemonLA/SkipToFullMoon.md)                      | Video         | All |
| [Apply Grits](PokemonLA/ApplyGrits.md)                                |               | All |
| [Pokédex Task Reader](PokemonLA/PokedexTasksReader.md)                | Video         | All |
||
| **Trading:** |
| [Self Box Trade](PokemonLA/SelfBoxTrade.md)                           | Video         | All |
| [Self Touch Trade](PokemonLA/SelfTouchTrade.md)                       | Video         | All |
||
| **Farming:** |
| [Nugget Farmer (Highlands)](PokemonLA/NuggetFarmerHighlands.md)       | Video + Audio | All |
| [Ingo Battle Grinder](PokemonLA/IngoBattleGrinder.md)                 | Video         | All |
| [Ingo Move Grinder](PokemonLA/IngoMoveGrinder.md)                     | Video         | All |
| [Magikarp Move Grinder](PokemonLA/MagikarpMoveGrinder.md)             | Video         | All |
| [Tenacity Candy Farmer](PokemonLA/TenacityCandyFarmer.md)             | Video         | All |
| [Leap Grinder](PokemonLA/LeapGrinder.md)                              | Video + Audio | All |
||
| **Shiny Hunting:** |
| [Alpha Crobat Hunter](PokemonLA/AlphaCrobatHunter.md)                 | Video + Audio | All |
| [Alpha Gallade Hunter](PokemonLA/AlphaGalladeHunter.md)               | Video + Audio | All |
| [Alpha Froslass Hunter](PokemonLA/AlphaFroslassHunter.md)             | Video + Audio | All |
| [Burmy Hunter](PokemonLA/BurmyHunter.md)                              | Video + Audio | All (Degraded: sbb2) |
| [Unown Hunter](PokemonLA/UnownHunter.md)                              | Video + Audio | All |
| [Shiny Hunt - Flag Pin](PokemonLA/ShinyHunt-FlagPin.md)               | Video + Audio | All |
| [Post-MMO Spawn Reset](PokemonLA/PostMMOSpawnReset.md)                | Video + Audio | All |
| [Shiny Hunt - Custom Path](PokemonLA/ShinyHunt-CustomPath.md)         | Video + Audio | All (Degraded: sbb2) |


## Pokémon Scarlet and Violet

| **Program** | **Description** | **Feedback** | **Controllers** |
| --- | --- | --- | --- |
| Game Settings | --- | --- | --- |
||
| **General:** |
| [Mass Purchase](PokemonSV/MassPurchase.md) | Purchase items from the shop.                                           | Video         | All |
| [Clothing Buyer](PokemonSV/ClothingBuyer.md) | Purchase clothing from shops.                                         | Video         | All |
| [Autonomous Ball Thrower](PokemonSV/AutonomousBallThrower.md) | Repeatedly throw a ball until you catch the pokemon. | Video         | All |
| [Size Checker](PokemonSV/SizeChecker.md) | Check boxes of Pokemon for size marks.                                    | Video         | All |
| [Self Box Trade](PokemonSV/SelfBoxTrade.md) | Tade boxes of Pokemon between two local Switches.                      | Video         | All |
| [Sandwich Maker](PokemonSV/SandwichMaker.md) | Make a sandwich  of your choice.                                      | Video         | All |
|| 
| **Boxes:** |
| [Mass Release](PokemonSV/MassRelease.md) | Mass release boxes of Pokemon.          | Video         | All |
| [Mass Attach Items](PokemonSV/MassAttachItems.md) | Mass attach items to Pokemon.  | Video         | All |
||
| **Farming:** |
| [LP Farmer](PokemonSV/LPFarmer.md) | Farm LP by day skipping Tera raids.                                                            | Video         | All (Degraded: sbb2) |
| [Gimmighoul Roaming Farmer](PokemonSV/GimmighoulRoamingFarmer.md) | Farm roaming Gimmighoul for coins.                              | Video         | All (Degraded: sbb2) |
| [Gimmighoul Chest Farmer](PokemonSV/GimmighoulChestFarmer.md) | Farm chest Gimmighoul for coins.                                    | Video         | Wired, Wireless |
| [Auction Farmer](PokemonSV/AuctionFarmer.md) | Farm special Pokeballs (now superceded by Item Printer RNG), EV reset berries, feathers | Video      | All (Degraded: sbb2) |
| [ESP Training](PokemonSV/ESPTraining.md) | Farm EV reset berries          	                                                        | Video         | All |
| [Tournament Farmer](PokemonSV/TournamentFarmer.md) | Farm money (now superceded by Item Printer RNG)                                | Video         | All |
| [Tournament Farmer 2](PokemonSV/TournamentFarmer2.md) | Farm money (now superceded by Item Printer RNG)                             | Video         | All |
| [Flying Trial Farmer](PokemonSV/FlyingTrialFarmer.md) | Farm Blueberry points (BP) with the Flying trial                            | Video         | Wired, Wireless |
| [BBQ Farmer](PokemonSV/BBQSoloFarmer.md)  | Farm Blueberry points (BP) with Blueberry quests                                        | Video + Audio | Wired, Wireless |
| [Material Farmer](PokemonSV/MaterialFarmer.md) | Farm Happiny dust                                                                  | Video + Audio | All |
| [Item Printer RNG](PokemonSV/ItemPrinterRNG.md) | Farm rare items (e.g. Ability Patch, PP Max, EXP Candy, rare Pokeballs, Tera shards). To farm money, farm and sell Ability Patches. | Video + Audio | All (Degraded: sbb2) |
||
| **Eggs:** |
| [Egg Fetcher](PokemonSV/EggFetcher.md) | Fetch eggs from a picnic.                         | Video         | All |
| [Egg Hatcher](PokemonSV/EggHatcher.md) | Hatch eggs from boxes.                            | Video         | All |
| [Egg Autonomous](PokemonSV/EggAutonomous.md) | Get meal power, fetch eggs, and hatch them. | Video         | All |
||
| **Tera Raids:** |
| [Auto-Host](PokemonSV/AutoHost.md) | Auto-host a Tera raid.                                                                     | Video         | All |
| [Tera Roller](PokemonSV/TeraRoller.md) | Roll Tera raids to find shiny Pokemon.                                                 | Video         | All (Degraded: sbb2) |
| [Tera Self Farmer](PokemonSV/TeraSelfFarmer.md) | Farm items and Pokemon from Tera raids. Hunt for shiny and high reward raids. | Video         | All (Degraded: sbb2) |
| [Tera Multi-Farmer](PokemonSV/TeraMultiFarmer.md) | Farm items and Pokemon from your own Tera raid using multiple Switches.     | Video         | All |
||
| **Fast Code Entry:** |
| [Fast Code Entry (FCE)](PokemonSV/FastCodeEntry.md) | Quickly enter a 4, 6, 8 digit link code.                                                      |               | All (Degraded, Wireless, sbb2) |
| [Clipboard Fast Code Entry (C-FCE)](PokemonSV/ClipboardFastCodeEntry.md) | Quickly enter a 4, 6, 8 digit link code from clipboard.                  |               | All (Degraded, Wireless, sbb2) |
| [Video Fast Code Entry (V-FCE)](PokemonSV/VideoFastCodeEntry.md) | Read a 4, 6, 8 digit link code from someone on your screen and enter it quickly. |               | All (Degraded, Wireless, sbb2) |
||
| **Stats Hunting:** |
| [Stats Reset](PokemonSV/StatsReset.md) | Repeatedly catch static encounters (e.g. Legendaries) until you get the stats you wish.         | Video         | All |
| [Stats Reset - Event Battle](PokemonSV/StatsResetEventBattle.md) | Repeatedly catch Ursaluna/Pecharunt until you get the stats you wish. | Video         | All |
||
| **Shiny Hunting:** |
| [Shiny Hunt - Area Zero Platform](PokemonSV/ShinyHunt-AreaZeroPlatform.md) | Shiny hunt Pokemon on the isolated platform at the bottom of Area Zero. | Video + Audio | All |
| [Shiny Hunt - Scatterbug](PokemonSV/ShinyHunt-Scatterbug.md) | Shiny hunt Scatterbug.                                                                | Video + Audio | All |
||
| **Glitches (v3.0.0):** |
| [Wild Item Farmer (cloning glitch)](PokemonSV/WildItemFarmer.md) | Farm an item held by a cloned wild Pokemon. (glitch patched) | Video         | All |
||
| **Glitches (v1.0.1):** |
| [Ride Cloner (1.0.1)](PokemonSV/RideCloner-101.md) | Clone your ride legendary and its item using the add-to-party glitch. (glitch patched) | Video         | Wired, Wireless |
| [Clone Items (1.0.1)](PokemonSV/CloneItems-101.md) | Clone items using the add-to-party glitch. (glitch patched)                            | Video         | Wired, Wireless |
||
| **Beta programs:** |
| [AutoStory](PokemonSV/AutoStory.md) | Progress through the tutorial and mainstory of Scarlet/Violet | Video         | Wired (Wireless untested) |
| [Claim Mystery Gift](PokemonSV/ClaimMysteryGift.md) | Claim the Mystery Gift in Scarlet/Violet | Video              | Wired (Wireless untested) |
||
| **Deprecated Programs:** |
| [Autonomous Item Printer](PokemonSV/AutoItemPrinter.md)               || Video         | All |


## Zelda: Tears of the Kingdom

| **Program** | **Feedback** | **Controllers** |
| --- | --- | --- |
| **Glitches (v1.1.1):** |
| [Bow Item Duper](ZeldaTotK/BowItemDuper.md)             |                  | Wired, Wireless |
| [Paraglide Item Duper](ZeldaTotK/ParaglideItemDuper.md) |                  | Wired, Wireless |
| [Shield Surf Item Duper](ZeldaTotK/SurfItemDuper.md)    |                  | Wired, Wireless |
| [Mineru Item Duper](ZeldaTotK/MineruItemDuper.md)       |                  | Wired, Wireless |

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)














