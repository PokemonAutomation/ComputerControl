# Program List (Computer Control)

This is a list of all the computer-control programs. To run these programs, you need the [computer-control setup](/Wiki/SetupGuide/README.md).

**Notes:**
- Programs that require video feedback cannot run on the Switch Lite because it does not have HDMI output.
- Not every program can run on every controller. Please check the table for compatibility.
- Table entries marked as "Degraded" mean that the program will run, but performance and reliability may be severely degraded.

**Jump To:**
- [Nintendo Switch](#nintendo-switch)
- [Pokémon Let's Go Pikachu/Eevee](#pok%C3%A9mon-lets-go-pikachueevee-lgpe)
- [Pokémon Sword/Shield](#pokémon-swordshield)
- [Pokémon Brilliant Diamond/Shining Pearl](#pokémon-brilliant-diamondshining-pearl)
- [Pokémon Legends Arceus](#pokémon-legends-arceus)
- [Pokémon Scarlet/Violet](#pokémon-scarlet-and-violet)
- [Zelda: Tears of the Kingdom](#zelda-tears-of-the-kingdom)

## Nintendo Switch

| **Program** | **Feedback** | **ESP32-WROOM** | **ESP32-S3<br>Arduino Uno R3/Leonardo<br>Teensy2/ProMicro** | **sys-botbase** |
| --- | --- | --- | --- | --- |
| [Framework Settings](NintendoSwitch/FrameworkSettings.md)         | --- | --- | --- | --- |
| [Virtual Console](NintendoSwitch/VirtualConsole.md)               | --- | Yes | Yes | Yes |
| [Switch Viewer](NintendoSwitch/SwitchViewer.md)                   | --- | Yes | Yes | Yes |
| [TurboA](NintendoSwitch/TurboA.md)                                |     | Yes | Yes | Yes |
| [Turbo Button](NintendoSwitch/TurboButton.md)                     |     | Yes | Yes | Yes |
| [Turbo Macro](NintendoSwitch/TurboMacro.md)                       |     | Yes | Yes | Yes |
| [Prevent Sleep](NintendoSwitch/PreventSleep.md)                   |     | Yes | Yes | Yes |
| [Friend Code Adder](NintendoSwitch/FriendCodeAdder.md)            |     | Yes | Yes | Degraded |
| [Friend Delete](NintendoSwitch/FriendDelete.md)                   |     | Yes | Yes | Yes |

## Pokémon Home

| **Program** | **Feedback** | **ESP32-WROOM** | **ESP32-S3<br>Arduino Uno R3/Leonardo<br>Teensy2/ProMicro** | **sys-botbase** |
| --- | --- | --- | --- | --- |
| [Page Swap](PokemonHome/PageSwap.md)                       |       | Yes | Yes | Yes |
| [Box Sorter](PokemonHome/BoxSorter.md)                     | Video | Yes | Yes |     |

## Pokémon Let's Go Pikachu/Eevee (LGPE)

Note that this game cannot be played with a Pro Controller. Therefore, ESP32 wireless is the only supported controller.

| **Program** | **Feedback** | **ESP32-WROOM** |
| --- | --- | --- |
| Game Settings | --- | --- | --- | --- |
||
| **General:** |
| [Daily Item Farmer](PokemonLGPE/DailyItemFarmer.md)  | Video | Yes |
||
| **Shiny Hunting:** |
| [Alolan Trade](PokemonLGPE/AlolanTrade.md)           | Video | Yes |
| [Fossil Revival](PokemonLGPE/FossilRevival.md)       | Video | Yes |
| [Gift Reset](PokemonLGPE/GiftReset.md)               | Video | Yes |
| [Legendary Reset](PokemonLGPE/LegendaryReset.md)     | Video | Yes |



## Pokémon Sword/Shield

| **Program** |  **Description** | **Feedback** | **ESP32-WROOM** | **ESP32-S3<br>Arduino Uno R3/Leonardo<br>Teensy2/ProMicro** | **sys-botbase** |
| --- | --- | --- | --- | --- | --- |
| [Game Settings](PokemonSwSh/PokemonSettings.md)        | --- | --- | --- | --- | --- |
||
| **QoL Macros:** |
| [Fast Code Entry (FCE)](PokemonSwSh/FastCodeEntry.md) |              |                  | Degraded | Yes | Degraded |
| [Friend Search Disconnect](PokemonSwSh/FriendSearchDisconnect.md) |  |                  | Yes | Yes | Yes |
||
| **General Programs:** |
| [Mass Release](PokemonSwSh/MassRelease.md) |                       |                  | Yes | Yes | Degraded |
| [Surprise Trade](PokemonSwSh/SurpriseTrade.md) |                   |                  | Yes | Yes |     |
| [Trade Bot](PokemonSwSh/TradeBot.md) |                             |                  | Yes | Yes |     |
| [Clothing Buyer](PokemonSwSh/ClothingBuyer.md) |                   |                  | Yes | Yes | Yes |
| [Autonomous Ball Thrower](PokemonSwSh/AutonomousBallThrower.md) |  | Video            | Yes | Yes | Yes |
| [Dex Rec Finder](PokemonSwSh/DexRecFinder.md) |                    | Video (Optional) | Yes | Yes | Degraded |
| [Box Reorder National Dex](PokemonSwSh/BoxReorderNationalDex.md) | | Video           | Yes | Yes |     |
||
| **Date-Spam Farmers:** |
| [Date Spam: Watt Farmer](PokemonSwSh/DateSpam-WattFarmer.md) | Farm watts. To farm money, use watts to buy Luxury balls, then sell them. || Degraded | Yes | Degraded |
| [Date Spam: Berry Farmer](PokemonSwSh/DateSpam-BerryFarmer.md) | Farm berries.                                                           || Yes | Yes | Degraded |
| [Date Spam: Berry Farmer 2](PokemonSwSh/DateSpam-BerryFarmer2.md) | Farm berries using audio/video feedback                              | Video + Audio | Yes | Yes | Degraded |
| [Date Spam: Loto Farmer](PokemonSwSh/DateSpam-LotoFarmer.md) |                          || Yes | Yes | Degraded |
| [Date Spam: Stow-On-Side Farmer](PokemonSwSh/DateSpam-StowOnSideFarmer.md) |            || Yes | Yes | Degraded |
| [Date Spam: Daily Highlight Farmer](PokemonSwSh/DateSpam-DailyHighlightFarmer.md) |     || Yes | Yes | Degraded |
| [Date Spam: Poké Jobs Farmer](PokemonSwSh/DateSpam-PokeJobsFarmer.md) |                 || Yes | Yes | Degraded |
||
| **Den Hunting:** |
| [Purple Beam Finder](PokemonSwSh/PurpleBeamFinder.md) |         | Video            | Yes | Yes | Yes |
| [Event Beam Finder](PokemonSwSh/EventBeamFinder.md) |           |                  | Yes | Yes | Yes |
| [Day Skipper (JPN)](PokemonSwSh/DaySkipperJPN.md) |             |                  |     | Yes |     |
| [Day Skipper (EU)](PokemonSwSh/DaySkipperEU.md) |               |                  |     | Yes |     |
| [Day Skipper (US)](PokemonSwSh/DaySkipperUS.md) |               |                  |     | Yes |     |
| [Day Skipper (JPN) - 7.8k](PokemonSwSh/DaySkipperJPN-7.8k.md) | |                  |     | Yes |     |
||
| **Hosting:** |
| [Den Roller](PokemonSwSh/DenRoller.md) |                    | Video (Optional) | Yes | Yes | Degraded |
| [Auto-Host Rolling](PokemonSwSh/AutoHost-Rolling.md) |      | Video (Optional) | Yes | Yes | Degraded |
| [Auto-Host Multi-Game](PokemonSwSh/AutoHost-MultiGame.md) | | Video (Optional) | Yes | Yes | Degraded |
||
| **Eggs:** |
| [Egg Fetcher 2](PokemonSwSh/EggFetcher2.md) |                              |       | Yes | Yes | Yes |
| [Egg Fetcher Multiple](PokemonSwSh/EggFetcherMultiple.md) |                |       | Yes | Yes | Yes |
| [Egg Hatcher](PokemonSwSh/EggHatcher.md) |                                 |       | Yes | Yes | Yes |
| [Egg Autonomous](PokemonSwSh/EggAutonomous.md) |                           | Video | Yes | Yes | Yes |
| [God Egg Item Duplication](PokemonSwSh/GodEggItemDuplication.md) |         |       | Yes | Yes | Degraded |
| [God Egg Duplication (developer only)](PokemonSwSh/GodEggDuplication.md) | |       | Yes | Yes | Degraded |
||
| **Non-Shiny Hunting:** |
| [Stats Reset](PokemonSwSh/StatsReset.md) |                   | Video | Yes | Yes | Yes |
| [Stats Reset - Calyrex](PokemonSwSh/StatsReset-Calyrex.md) | | Video | Yes | Yes | Yes |
| [Stats Reset - Moltres](PokemonSwSh/StatsReset-Moltres.md) | | Video | Yes | Yes | Yes |
| [Stats Reset - Regi](PokemonSwSh/StatsReset-Regi.md) |       | Video | Yes | Yes | Yes |
||
| **Shiny Hunting:** |
| [Multi-Game Fossil Revive](PokemonSwSh/MultiGameFossil.md) |                                      |                  | Yes | Yes | Degraded |
| [Curry Hunter](PokemonSwSh/CurryHunter.md) |                                                      | Video (Optional) | Yes | Yes |     |
| [Shiny Hunt Autonomous - Regi](PokemonSwSh/ShinyHuntAutonomous-Regi.md) |                         | Video | Yes | Yes | Degraded |
| [Shiny Hunt Autonomous - Swords Of Justice](PokemonSwSh/ShinyHuntAutonomous-SwordsOfJustice.md) | | Video | Yes | Yes | Yes |
| [Shiny Hunt Autonomous - Strong Spawn](PokemonSwSh/ShinyHuntAutonomous-StrongSpawn.md) |          | Video | Yes | Yes | Yes |
| [Shiny Hunt Autonomous - Regigigas2](PokemonSwSh/ShinyHuntAutonomous-Regigigas2.md) |             | Video | Yes | Yes | Yes |
| [Shiny Hunt Autonomous - IoA Trade](PokemonSwSh/ShinyHuntAutonomous-IoATrade.md) |                | Video | Yes | Yes | Yes |
| [Shiny Hunt Autonomous - Berry Tree](PokemonSwSh/ShinyHuntAutonomous-BerryTree.md) |              | Video | Yes | Yes | Degraded |
| [Shiny Hunt Autonomous - Whistling](PokemonSwSh/ShinyHuntAutonomous-Whistling.md) |               | Video | Yes | Yes | Yes |
| [Shiny Hunt Autonomous - Fishing](PokemonSwSh/ShinyHuntAutonomous-Fishing.md) |                   | Video | Yes | Yes | Yes |
| [Shiny Hunt Autonomous - Overworld](PokemonSwSh/ShinyHuntAutonomous-Overworld.md) |               | Video | Yes | Yes | Yes |
||
| **RNG:** |
| [RNG Seed Finder](PokemonSwSh/SeedFinder.md) | Finds the current state to be used for manual RNG manipulation      | Video | Yes | Yes | Yes |
| [Cram-o-matic RNG](PokemonSwSh/CramomaticRNG.md) | Farm apriballs using RNG manip of Cram-o-matic                  | Video | Yes | Yes | Degraded |
||
| **Multi-Switch Programs:** |
| Synchronized Spinning |                                                    || Yes | Yes | Degraded |
| [Raid Item Farmer (OHKO)](PokemonSwSh/RaidItemFarmerOHKO.md)  |            || Yes | Yes |      |
||
| [**Auto Max Lair 2.0:**](PokemonSwSh/MaxLair.md) |
| [Max Lair: Standard](PokemonSwSh/MaxLair-Standard.md) | Run Dynamax Adventures until a shiny Legendary is found.               | Video | Yes | Yes | Yes |
| [Max Lair: Strong Boss](PokemonSwSh/MaxLair-StrongBoss.md) | Run Dynamax Adventures and intelligently reset to keep paths with high win rates (for Legendaries that are hard to beat) | Video | Yes | Yes | Yes |
| [Max Lair: Boss Finder](PokemonSwSh/MaxLair-BossFinder.md) | Run Dynamax Adventures until you find the boss you want.          | Video | Yes | Yes | Yes |
||
| **Deprecated Programs:** |
||
| [Ball Thrower](PokemonSwSh/BallThrower.md) |                      |                  | Yes | Yes | Yes |
| [Beam Reset](PokemonSwSh/BeamReset.md) |                                   |       | Yes | Yes |     |
| [Egg Combined 2](PokemonSwSh/EggCombined2.md) |                            |       | Yes | Yes |     |
| [Egg Super-Combined 2](PokemonSwSh/EggSuperCombined2.md) |                 |       | Yes | Yes |     |
| [Shiny Hunt Unattended - Regi](PokemonSwSh/ShinyHuntUnattended-Regi.md) |                         |                  | Yes | Yes |     |
| [Shiny Hunt Unattended - Swords Of Justice](PokemonSwSh/ShinyHuntUnattended-SwordsOfJustice.md) | |                  | Yes | Yes |     |
| [Shiny Hunt Unattended - Strong Spawn](PokemonSwSh/ShinyHuntUnattended-StrongSpawn.md) |          |                  | Yes | Yes |     |
| [Shiny Hunt Unattended - Regigigas2](PokemonSwSh/ShinyHuntUnattended-Regigigas2.md) |             |                  | Yes | Yes |     |
| [Shiny Hunt Unattended - IoA Trade](PokemonSwSh/ShinyHuntUnattended-IoATrade.md) |                |                  | Yes | Yes |     |


## Pokémon Brilliant Diamond/Shining Pearl

| **Program** | **Feedback** | **ESP32-WROOM** | **ESP32-S3<br>Arduino Uno R3/Leonardo<br>Teensy2/ProMicro** | **sys-botbase** |
| --- | --- | --- | --- | --- |
| Game Settings | --- | --- | --- | --- |
||
| **General:** |
| [Mass Release](PokemonBDSP/MassRelease.md)                            |       | Yes | Yes | Yes |
| [Autonomous Ball Thrower](PokemonBDSP/AutonomousBallThrower.md)       | Video | Yes | Yes | Yes |
||
| **Trading:** |
| [Self Box Trade](PokemonBDSP/SelfBoxTrade.md)                         | Video | Yes | Yes | Yes |
| [Self Touch Trade](PokemonBDSP/SelfTouchTrade.md)                     | Video | Yes | Yes | Yes |
||
| **Farming:** |
| [Money Farmer (Route 212)](PokemonBDSP/MoneyFarmerRoute212.md)        | Video | Yes | Yes |     |
| [Money Farmer (Route 210)](PokemonBDSP/MoneyFarmerRoute210.md)        | Video | Yes | Yes |     |
| [Double Battle Leveling](PokemonBDSP/DoublesLeveling.md)              | Video | Yes | Yes | Yes |
| [Amity Square Pick Up Farmer](PokemonBDSP/AmitySquarePickUpFarmer.md) |       | Yes | Yes | Yes |
| [Gift Berry Reset](PokemonBDSP/GiftBerryReset.md)                     | Video | Yes | Yes | Yes |
| [Poffin Cooker](PokemonBDSP/PoffinCooker.md)                          | Video | Yes | Yes | Degraded |
||
| **Shiny Hunting:** |
| [Starter Reset](PokemonBDSP/StarterReset.md)                          | Video | Yes | Yes | Yes |
| [Legendary Reset](PokemonBDSP/LegendaryReset.md)                      | Video | Yes | Yes | Yes |
| [Shiny Hunt - Overworld](PokemonBDSP/ShinyHunt-Overworld.md)          | Video | Yes | Yes | Yes |
| [Shiny Hunt - Fishing](PokemonBDSP/ShinyHunt-Fishing.md)              | Video | Yes | Yes | Yes |
| [Shiny Hunt - Shaymin](PokemonBDSP/ShinyHunt-Shaymin.md)              | Video | Yes | Yes | Yes |
||
| **Eggs:** |
| [Egg Fetcher](PokemonBDSP/EggFetcher.md)                              |       | Yes | Yes | Yes |
| [Egg Hatcher](PokemonBDSP/EggHatcher.md)                              |       | Yes | Yes | Yes |
| [Egg Autonomous](PokemonBDSP/EggAutonomous.md)                        | Video | Yes | Yes | Yes |
||
| **Glitches (v1.1.3):** |
| [Activate Menu Glitch (1.1.3)](PokemonBDSP/ActivateMenuGlitch-113.md)     | Video | Yes | Yes |     |
| [Clone Items (Box Copy Method 2)](PokemonBDSP/CloneItemsBoxCopy2.md)      | Video | Yes | Yes |     |
||
| **Glitches (v1.1.2):** |
| [Activate Menu Glitch (1.1.2)](PokemonBDSP/ActivateMenuGlitch-Poketch.md) | Video | Yes | Yes |     |


## Pokémon Legends Arceus

| **Program** | **Feedback** | **ESP32-WROOM** | **ESP32-S3<br>Arduino Uno R3/Leonardo<br>Teensy2/ProMicro** | **sys-botbase** |
| --- | --- | --- | --- | --- |
| Game Settings | --- | --- | --- | --- |
||
| **General:** |
| [Braviary Height Glitch](PokemonLA/BraviaryHeightGlitch.md)           |               | Yes | Yes | Yes |
| [Distortion Waiter](PokemonLA/DistortionWaiter.md)                    | Video         | Yes | Yes | Yes |
| [Outbreak Finder](PokemonLA/OutbreakFinder.md)                        | Video         | Yes | Yes | Yes |
| [Clothing Buyer](PokemonLA/ClothingBuyer.md)                          |               | Yes | Yes | Yes |
| [Skip To Full Moon](PokemonLA/SkipToFullMoon.md)                      | Video         | Yes | Yes | Yes |
| [Apply Grits](PokemonLA/ApplyGrits.md)                                |               | Yes | Yes | Yes |
| [Pokédex Task Reader](PokemonLA/PokedexTasksReader.md)                | Video         | Yes | Yes | Yes |
||
| **Trading:** |
| [Self Box Trade](PokemonLA/SelfBoxTrade.md)                           | Video         | Yes | Yes | Yes |
| [Self Touch Trade](PokemonLA/SelfTouchTrade.md)                       | Video         | Yes | Yes | Yes |
||
| **Farming:** |
| [Nugget Farmer (Highlands)](PokemonLA/NuggetFarmerHighlands.md)       | Video + Audio | Yes | Yes | Yes |
| [Ingo Battle Grinder](PokemonLA/IngoBattleGrinder.md)                 | Video         | Yes | Yes | Yes |
| [Ingo Move Grinder](PokemonLA/IngoMoveGrinder.md)                     | Video         | Yes | Yes | Yes |
| [Magikarp Move Grinder](PokemonLA/MagikarpMoveGrinder.md)             | Video         | Yes | Yes | Yes |
| [Tenacity Candy Farmer](PokemonLA/TenacityCandyFarmer.md)             | Video         | Yes | Yes | Yes |
| [Leap Grinder](PokemonLA/LeapGrinder.md)                              | Video + Audio | Yes | Yes | Yes |
||
| **Shiny Hunting:** |
| [Alpha Crobat Hunter](PokemonLA/AlphaCrobatHunter.md)                 | Video + Audio | Yes | Yes | Yes |
| [Alpha Gallade Hunter](PokemonLA/AlphaGalladeHunter.md)               | Video + Audio | Yes | Yes | Yes |
| [Alpha Froslass Hunter](PokemonLA/AlphaFroslassHunter.md)             | Video + Audio | Yes | Yes | Yes |
| [Burmy Hunter](PokemonLA/BurmyHunter.md)                              | Video + Audio | Yes | Yes | Degraded |
| [Unown Hunter](PokemonLA/UnownHunter.md)                              | Video + Audio | Yes | Yes | Yes |
| [Shiny Hunt - Flag Pin](PokemonLA/ShinyHunt-FlagPin.md)               | Video + Audio | Yes | Yes | Yes |
| [Post-MMO Spawn Reset](PokemonLA/PostMMOSpawnReset.md)                | Video + Audio | Yes | Yes | Yes |
| [Shiny Hunt - Custom Path](PokemonLA/ShinyHunt-CustomPath.md)         | Video + Audio | Yes | Yes | Degraded |


## Pokémon Scarlet and Violet

| **Program** | **Description** | **Feedback** | **ESP32-WROOM** | **ESP32-S3<br>Arduino Uno R3/Leonardo<br>Teensy2/ProMicro** | **sys-botbase** |
| --- | --- | --- | --- | --- | --- |
| Game Settings | --- | --- | --- | --- | --- |
||
| **General:** |
| [Mass Purchase](PokemonSV/MassPurchase.md) | Purchase items from the shop.                                           | Video         | Yes | Yes | Yes |
| [Clothing Buyer](PokemonSV/ClothingBuyer.md) | Purchase clothing from shops.                                         | Video         | Yes | Yes | Yes |
| [Autonomous Ball Thrower](PokemonSV/AutonomousBallThrower.md) | Repeatedly throw a ball until you catch the pokemon. | Video         | Yes | Yes | Yes |
| [Size Checker](PokemonSV/SizeChecker.md) | Check boxes of Pokemon for size marks.                                    | Video         | Yes | Yes | Yes |
| [Self Box Trade](PokemonSV/SelfBoxTrade.md) | Tade boxes of Pokemon between two local Switches.                      | Video         | Yes | Yes | Yes |
| [Sandwich Maker](PokemonSV/SandwichMaker.md) | Make a sandwich  of your choice.                                      | Video         | Yes | Yes | Yes |
|| 
| **Boxes:** |
| [Mass Release](PokemonSV/MassRelease.md) | Mass release boxes of Pokemon.          | Video         | Yes | Yes | Yes |
| [Mass Attach Items](PokemonSV/MassAttachItems.md) | Mass attach items to Pokemon.  | Video         | Yes | Yes | Yes |
||
| **Farming:** |
| [LP Farmer](PokemonSV/LPFarmer.md) | Farm LP by day skipping Tera raids.                                                            | Video         | Yes | Yes | Degraded |
| [Gimmighoul Roaming Farmer](PokemonSV/GimmighoulRoamingFarmer.md) | Farm roaming Gimmighoul for coins.                              | Video         | Yes | Yes | Degraded |
| [Gimmighoul Chest Farmer](PokemonSV/GimmighoulChestFarmer.md) | Farm chest Gimmighoul for coins.                                    | Video         | Yes | Yes |     |
| [Auction Farmer](PokemonSV/AuctionFarmer.md) | Farm special Pokeballs (now superceded by Item Printer RNG), EV reset berries, feathers | Video         | Yes | Yes | Degraded |
| [ESP Training](PokemonSV/ESPTraining.md) | Farm EV reset berries          	                                                        | Video         | Yes | Yes | Yes |
| [Tournament Farmer](PokemonSV/TournamentFarmer.md) | Farm money (now superceded by Item Printer RNG)                                | Video         | Yes | Yes | Yes |
| [Tournament Farmer 2](PokemonSV/TournamentFarmer2.md) | Farm money (now superceded by Item Printer RNG)                             | Video         | Yes | Yes | Yes |
| [Flying Trial Farmer](PokemonSV/FlyingTrialFarmer.md) | Farm Blueberry points (BP) with the Flying trial                            | Video         | Yes | Yes |     |
| [BBQ Farmer](PokemonSV/BBQSoloFarmer.md)  | Farm Blueberry points (BP) with Blueberry quests                                        | Video + Audio | Yes | Yes |     |
| [Material Farmer](PokemonSV/MaterialFarmer.md) | Farm Happiny dust                                                                  | Video + Audio | Yes | Yes | Yes |
| [Item Printer RNG](PokemonSV/ItemPrinterRNG.md) | Farm rare items (e.g. Ability Patch, PP Max, EXP Candy, rare Pokeballs, Tera shards). To farm money, farm and sell Ability Patches. | Video + Audio | Yes | Yes | Degraded |
||
| **Eggs:** |
| [Egg Fetcher](PokemonSV/EggFetcher.md) | Fetch eggs from a picnic.                         | Video         | Yes | Yes | Yes |
| [Egg Hatcher](PokemonSV/EggHatcher.md) | Hatch eggs from boxes.                            | Video         | Yes | Yes | Yes |
| [Egg Autonomous](PokemonSV/EggAutonomous.md) | Get meal power, fetch eggs, and hatch them. | Video         | Yes | Yes | Yes |
||
| **Tera Raids:** |
| [Auto-Host](PokemonSV/AutoHost.md) | Auto-host a Tera raid.                                                                     | Video         | Yes | Yes | Yes |
| [Tera Roller](PokemonSV/TeraRoller.md) | Roll Tera raids to find shiny Pokemon.                                                 | Video         | Yes | Yes | Degraded |
| [Tera Self Farmer](PokemonSV/TeraSelfFarmer.md) | Farm items and Pokemon from Tera raids. Hunt for shiny and high reward raids. | Video         | Yes | Yes | Degraded |
| [Tera Multi-Farmer](PokemonSV/TeraMultiFarmer.md) | Farm items and Pokemon from your own Tera raid using multiple Switches.     | Video         | Yes | Yes | Yes |
||
| **Fast Code Entry:** |
| [Fast Code Entry (FCE)](PokemonSV/FastCodeEntry.md) | Quickly enter a 4, 6, 8 digit link code.                                                      |               | Degraded | Yes | Degraded |
| [Clipboard Fast Code Entry (C-FCE)](PokemonSV/ClipboardFastCodeEntry.md) | Quickly enter a 4, 6, 8 digit link code from clipboard.                  |               | Degraded | Yes | Degraded |
| [Video Fast Code Entry (V-FCE)](PokemonSV/VideoFastCodeEntry.md) | Read a 4, 6, 8 digit link code from someone on your screen and enter it quickly. |               | Degraded | Yes | Degraded |
||
| **Stats Hunting:** |
| [Stats Reset](PokemonSV/StatsReset.md) | Repeatedly catch static encounters (e.g. Legendaries) until you get the stats you wish.         | Video         | Yes | Yes | Yes |
| [Stats Reset - Event Battle](PokemonSV/StatsResetEventBattle.md) | Repeatedly catch Ursaluna/Pecharunt until you get the stats you wish. | Video         | Yes | Yes | Yes |
||
| **Shiny Hunting:** |
| [Shiny Hunt - Area Zero Platform](PokemonSV/ShinyHunt-AreaZeroPlatform.md) | Shiny hunt Pokemon on the isolated platform at the bottom of Area Zero. | Video + Audio | Yes | Yes | Yes |
| [Shiny Hunt - Scatterbug](PokemonSV/ShinyHunt-Scatterbug.md) | Shiny hunt Scatterbug.                                                                | Video + Audio | Yes | Yes | Yes |
||
| **Glitches (v3.0.0):** |
| [Wild Item Farmer (cloning glitch)](PokemonSV/WildItemFarmer.md) | Farm an item held by a cloned wild Pokemon. (glitch patched) | Video         | Yes | Yes | Yes |
||
| **Glitches (v1.0.1):** |
| [Ride Cloner (1.0.1)](PokemonSV/RideCloner-101.md) | Clone your ride legendary and its item using the add-to-party glitch. (glitch patched) | Video         | Yes | Yes |     |
| [Clone Items (1.0.1)](PokemonSV/CloneItems-101.md) | Clone items using the add-to-party glitch. (glitch patched)                            | Video         | Yes | Yes |     |
||
| **Beta programs:** |
| [AutoStory](PokemonSV/AutoStory.md) | Progress through the tutorial and mainstory of Scarlet/Violet | Video         | Untested | Yes |     |
||
| **Deprecated Programs:** |
| [Autonomous Item Printer](PokemonSV/AutoItemPrinter.md)               | Video         | Yes | Yes | Yes |


## Zelda: Tears of the Kingdom

| **Program** | **Feedback** | **ESP32-WROOM** | **ESP32-S3<br>Arduino Uno R3/Leonardo<br>Teensy2/ProMicro** | **sys-botbase** |
| --- | --- | --- | --- | --- |
| **Glitches (v1.1.1):** |
| [Bow Item Duper](ZeldaTotK/BowItemDuper.md)             |                  | Yes | Yes |     |
| [Paraglide Item Duper](ZeldaTotK/ParaglideItemDuper.md) |                  | Yes | Yes |     |
| [Shield Surf Item Duper](ZeldaTotK/SurfItemDuper.md)    |                  | Yes | Yes |     |
| [Mineru Item Duper](ZeldaTotK/MineruItemDuper.md)       |                  | Yes | Yes |     |

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)



