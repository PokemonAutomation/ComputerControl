# Version History

### 2021-10-10:
- New wiki that splits Microcontroller and Computer-Control programs.

***

Everything from here on down is from the old combined repo that includes both native and serial programs.

### 2021-09-16:
- More fixes for date-spam break on firmware 13.
- Added Calyrex auto-catching and stats reset.
- Discord notifications can now be sent to multiple webhooks instead of just one.
- Added test buttons for Discord webhook notifications.

### 2021-09-14:
- Fixed date-spam break for firmware 13.

### 2021-08-26:
- Fixed an issue in the SurpriseTrade config that made it disappear from the HexGenerator.
- Den Roller can now recognize silhouettes and automatically stop on a specific Pokemon. So now you can easily roll for g-maxes and other 1% rolls.
- Overworld, fishing, whistling, and berry tree encounter bots now support auto-catching.
- Added Autonomous Ball Thrower.
- Added Regi auto-catch and Stats Reset.
- Added Moltres auto-catch Stats Reset.
- Discord notifications are now sent when a program stops due to an error.
- Discord notifications are also sent for auto-catching.
- Discord notifications now include a screenshot of encounter bot shinies.
- Numerous internal changes and refactors.

### 2021-07-31:
- Added Curry Hunter. You can now hunt for camp shinies!
- Documention links updated to point to the wiki.
- Encounter bot filtering. You can now choose what shinies/species to stop or run from.
- Added Discord webhook notifications. Get updates and notifications of your shiny hunts on your private server!
- Added an option to start programs in-game instead of the grip menu.
- Shiny detection will no longer false positive on dive balls and your own lead shiny.
- Fixed a bug in the overworld bot where mark prioritization did not always work.
- Minor adjustments to overworld bot.

### 2021-06-30:
- Native Programs: New directory structure and HexGenerator layout to make room for BDSP and future games.
- Native Programs: Mac build scripts no longer use its own FZF binary to avoid permission errors.
- Serial Programs: Lots of changes to prepare for BDSP and future games.
- New Program: Stats Reset. Reset gift Pokemon for the desired stats. (Type: Null, Cosmog, Poipole)
- New Program: Turbo Button. It is a more generalized version of Turbo A for any button.
- The Dex Rec Finder now supports feedback. You can specify what Pokemon you're looking for and it will stop when it finds it.
- The Dex Rec Finder can now run on the Uno R3.
- Purple Beam Finder is more accurate at detecting beam types.
- Day skippers now show stats.
- Berry tree, whistling, fishing, and overworld encounter bots will read the Pokemon that you encounter, log it, and show encounter statistics.
- Overworld encounter bot has new settings that will work in Glimwood Tangle.

### 2021-05-24:
- Added Pokedex Recommendation Finder.
- Purple Beam Finder has fewer purple beam false positives.
- The fishing bot now works in Motostoke.
- Numerous other minor big fixes.

### 2021-05-14:
- Added Overworld Encounter Bot.
- Added Pokemon Home page swap.
- Fix an issue in the HexGenerator that may prevent it from working on file paths with spaces.
- Fixed a bug AutoHost-MultiGame where it may improperly save the number of day skips.

### 2021-05-06:
- Fixed an issue in the shiny detection for autonomous SoJ.
- Autonomous shiny hunting programs now use feedback when running from an encounter.
- Autonomous whistling and berry tree shiny hunt are now more smooth.

### 2021-04-30:
- Fix a stats tracking bug in autonomous IoA trade.

### 2021-04-17:
- Added the autonomous shiny hunting programs.
- Added stats tracking.
- Added troll-hosting to AutoHost-Rolling.
- Numerous bug fixes.

### 2021-03-26:
- Added troll-hosting option to AutoHost-Rolling. (native programs only)

### 2021-03-22:
- The HexGenerator will display a warning when run from a path containing non-ASCII characters.

### 2021-03-19:
- Increased exit building delay for Regi shiny hunting.
- Default correction interval for Regi programs has been increased to 10.
- Fixed an issue where date spamming misses the date.
- Programs that stop will no longer keep the Switch from sleeping. If you don't want your Switch to sleep after going idle, you need to disable this in the system settings.
- Keyboard mapping can be configured in the json settings file. It is not user friendly, but better than nothing.
- Bugfixes and improved stability for the serial programs application.

### 2021-03-08:
- For serial programs, auto-hosts will be close the game as soon as the raid starts. This reduces freezes.

### 2021-03-07:
- Fixed some application hangs in SerialPrograms.
- Improved stability of Regieleki shiny hunt.

### 2021-03-06:
- Fixed a bug in PABotBase that can cause the controller to freeze.
- Fixed an issue in the HexGenerator that prevented you from saving settings.
- Added Purple Beam Finder. A smart version of BeamReset that will automatically stop on a purple beam and make noise to notify you!
- Autohosts now support feedback. If the lobby is full and everyone is ready, the raid will start early. If someone is not ready, it will wait instead of crashing the raid. Video feedback is still optional. Without it, the autohosts behave the same as before.

### 2021-02-25:
- Officially added SerialPrograms to the public releases.
- Added OHKO den farmer for Exp Candy farming.

### 2021-02-20:
- Added CustomProgram to let you write your own programs!

### 2021-02-15:
- Adjust serial connection delays and timeouts.
- Fixed some program hangs.

### 2021-02-14:
- Officially added SerialPrograms to the project.
- BeamReset now uses `TOLERATE_SYSTEM_UPDATE_MENU_SLOW` instead of `TOLERATE_SYSTEM_UPDATE_MENU_FAST`.

### 2021-02-13:
- Increased default delete time for FriendDelete.
- Removed the PDF manual. Use the online documentation instead.

### 2021-02-12:
- TradeBot now has an option to handle the extra line of text in German.
- EggCombined2 and EggSuperCombined2 now support rollover prevention.

### 2021-01-30:
- Replace MCU selection with board selection.
- Added support for the Pro Micro board.

### 2021-01-25:
- Fixed incorrect counting for Regigigas hunting serial logging.

### 2021-01-21:
-  Added an alternate launch script because the main one keeps getting nuked by virus scanners.
-  The UI now shows full file paths.

### 2021-01-18:
-  UI will now log errors to a file.

### 2021-01-14:
-  Fix incorrect default `DELAY_TO_SELECT_MOVE` value for the auto-hosts in the UI.

### 2021-01-13:
-  Fix line endings in the new Unix scripts.

### 2021-01-12:
-  Faster Regidrago and Regice light patterns.
-  Fixed a bug in the raid count logging for AutoHost-MultiGame.

### 2021-01-09:
-  joyrida’s improvements to Mac and Unix build scripts.

### 2021-01-08:
-  Minor adjustment to the BallThrower program.
-  The UI should be able to build even if the PATH is set incorrectly if WinAVR is installed in the default place.
-  Added an online version of this manual.
-  The UI will now link to the relevant section of the online manual.

### 2021-01-07:
-  Fixed a stability issue in Regidrago shiny hunt.

### 2021-01-05:
-  Fix some DPI scaling problems with the UI.

### 2021-01-03:
-  Regirock shiny hunting is slightly faster and more reliable.

### 2021-01-02:
-  Update manual to include the method of subtracting 250 ticks to calibrate the unattended shiny hunt programs.
-  Update manual to include the hex generator UI.

### 2021-01-01:
-  Add an option to the UI to configure global settings.
-  Minor optimizations to ShinyHuntUnattended-Regi.

### 2020-12-31:
-  UI: Proper text wrapping.
-  UI: Added button to save settings, but not compile.

### 2020-12-30:
-  Added UI program to build .hex files in Windows.

### 2020-12-29:
-  Windows built-all scripts will automatically clean if the existing build artifacts are of a different MCU.

### 2020-12-25:
-  Change default year for US and EU day skippers to 2021.
-  Move some of the PABotBase subroutines from device to client.
-  Fixed some bugs in PABotBase.

### 2020-12-24:
-  Fix some reliability issues with EggCombined2 and EggSuperCombined2.

### 2020-12-23:
-  Added section on setting up serial communication.
-  PABotBase device and client now mutually support request and command queuing.

### 2020-12-21:
-  Egg hatchers stop spinning 20 seconds before they enter the box system. This prevents late hatching eggs from breaking the program by blocking the box operations.
-  ShinyHuntUnattended-Regigigas2 is slightly faster.
-  More updates to PABotBase.

### 2020-12-18:
-  Adjusted default timings for ShinyHuntUnattended-Regigigas2.
-  Added more functions to PABotBase.

### 2020-12-16:
-  Added preliminary support for serial communication. All programs now listen to serial commands. Some programs will also broadcast status information over serial.
-  Added PABotBase for computer-based programs. Software to control the bot will come later.

### 2020-12-13:
-  ShinyHuntUnattended-Regigigas2 is now enable in the public releases.
-  EggHatcher now uses the global box operation timings. This should fix an issue some people are encountering.
-  Continued internal refactoring.

### 2020-12-11:
-  Fixed another issue in some of the unattended shiny-hunt programs that prevented them from properly bypassing the system update window.
-  More internal refactoring.

### 2020-12-09:
-  Large restructure of the repository.

### 2020-12-08:
-  Fixed another issue in the BallThrower program.
-  Egg fetch and egg combined programs are more tolerant to eggs that take longer to fetch.
-  Egg fetch timing can now be configured.
-  For den rolling when TOLERATE_SYSTEM_UPDATE_MENU_SLOW is enabled, the timings for entering and exiting the Switch Pokemon menu can now be configured.

### 2020-12-06a:
-  Added ShinyHuntUnattended-Regigigas2 for beta testing.


### 2020-12-06:
-  Build scripts for Windows will now tell you if are trying to run it without unzipping the package.

### 2020-12-05:
-  Added ShinyHuntUnattended-IoATrade for beta testing.

### 2020-12-03:
-  Critical Fix: Remove update window avoidance from BallThrower. It causes the program to run from the battle.

### 2020-12-02:
-  Added BallThrower.
-  Fixed an incorrect type used for EggSuperCombined2.

### 2020-12-01:
-  Renamed all “SoftReset” programs to “ShinyHunt” programs.
-  Refactored all the system update window bypassing logic and options.

### 2020-11-30:
-  All soft-reset programs will now tolerate the system update window.

### 2020-11-29:
-  EggCombined2 and EggSuperCombined2 now use bike boosts for the return trip.

### 2020-11-28:
-  Egg fetching now does bike boosts on return trip instead of away trip.

### 2020-11-27:
-  Added DateSpam-DailyHighlightFarmer.
-  Renamed all the date-spam farmers so they sort together.
-  In GodEggItemDupe, the delay to enter your party now uses the “MENU_TO_POKEMON_DELAY” parameter in Settings.c.
-  Removed AutoHost-Airplane and AutoHost-FriendSearch. Use softlock camp method instead.
-  Refactored this manual.

### 2020-11-19:
-  Add rollover prevention to SR programs for Regi and Regigigas.
-  Add time rollback to SR programs for Swords of Justice and strong spawns.

### 2020-11-15:
-  Add SoftResetUnattended-Regigigas.

### 2020-11-13:
-  Minor adjustments to light puzzles for Registeel and Regieleki to improve reliability.

### 2020-11-11:
-  Add SoftResetUnattended-StrongSpawn.
-  Add an option to LotoFarmer to control how long to mash B. Needed for German.

### 2020-11-09:
-  Revert the default correction period of SoftResetUnattended-Regi back to 5.

### 2020-11-07:
-  Added beta build scripts for Mac and Unix/Linux.
-  Adjust the correction timings for SoftResetUnattended-Regi.
-  Increase default correction period from 5 to 10 for SoftResetUnattended-Regi.
-  Add an option to BeamReset to handle the extra line in German.
-  Removed AutoHost-Sleep. There are better methods for softlock hosting now.

### 2020-10-31c:
-  Fixed an issue in Regi unattended SR where it gets stuck on the statue after running.
-  Added support for backups saves to AutoHost-Rolling and AutoHost-MultiGame. This allows for the camp+backup save method for softlock auto-hosting.

### 2020-10-31:
-  Added support for Regieleki and Regidrago to SoftResetUnattended-Regi.

### 2020-10-30:
-  Added SoftResetUnattended-Regi: Unattended SR for Regi golems that will stop on a shiny.

### 2020-10-27:
-  SoftResetUnattended-SwordsOfJustice: Improve locking mechanism and add support for airplane mode.

### 2020-10-26:
-  Added SoftResetUnattended-SwordsOfJustice: Unattended SR for SOJs that will stop on a shiny.

### 2020-10-25:
-  Added SoftReset-SwordsOfJustice to soft-reset for the Sword of Justice legendaries.
-  Renamed some of the programs.

### 2020-10-24:
-  Added SoftResetRegi to soft-reset for the Regi golem legendaries.

### 2020-10-22:
-  Fixed game entry timings for Crown Tundra DLC.
-  Removed EggCombined and EggSuperCombined. Use the new ones instead.

### 2020-10-16:
-  Fixed an error in the manual for AutoHostFriendSearch.
-  Removed EggFetcher since it has been superseded by EggFetcher2.

### 2020-10-15:
-  Added second generation combined egg hatchers: EggCombined2 and EggSuperCombined2

### 2020-10-12:
-  GodEggItemDupe now uses the faster triangulation method. Thus it now requires a fully upgraded bike.

### 2020-10-11:
-  Fixed an issue in AutoHostRolling where rollover protection didn't work.
-  Internal refactorings.

### 2020-10-09:
-  EggCombined and EggSuperCombined now support non-integer fetches per batch. This is achieved by varying the # of fetches per batch so that they average out to the specified target. This will allow for better fine-tuning of fetch rates.
-  DaySkipperJPN-7.8k now uses the year instead of (year - 2000) to reduce confusion.

### 2020-09-30:
-  Fixed some errors in the manual.

### 2020-09-27:
-  Increased the default start game delay by 2 seconds to better accommodate slower Switches.
-  Revamped the handling of uncatchable Pokémon. Uncatchable prompt avoidance can now be configured on a per-program basis. For AutoHostMultiGame, it can be configured on a per-game basis.

### 2020-09-26:
-  All programs that receive Pokémon must now have “Send to Boxes” set to “Automatic”.
-  Added a global setting that speeds up certain programs when “Send to Boxes” is set to “Automatic”. This new option is enabled by default.
-  EggCombined, EggSuperCombined, and MultiGameFossil are now slightly faster due to the above.
-  Added EggFetcher2 which uses the triangulation method to avoid fly-backs.

### 2020-09-21:
-  Slightly improved reliability of date-skipping for den rolling.
-  Added a note for the day skippers about airplane mode and non-primary Switch digital games.
-  Added some more setup instructions for Arduino and Teensy.
-  Added a hardware recommendations section.
-  Added a start program callback to complement the end program callback.

### 2020-09-11:
-  Minor timing changes to improve stability for game-switching programs. (i.e. multi-host and fossils)
-  Fixed a stability issue with the code entry. Some codes will be a tiny bit slower.

### 2020-09-09:
-  Reduced memory footprint for all programs.
-  The !BuildAll scripts will now work even if you run them from the wrong working directory.

### 2020-09-07:
-  The !BuildAll scripts will now tell you if WinAVR isn’t installed.
-  AutoHostRolling now closes the game before it rolls back the date for the next run.
-  AutoHostFriendSearch now disconnects one second earlier to compensate for the extra time needed to navigate all the way into the user profile.

### 2020-09-04:
-  Added DaySkipperJPN-7.8k. A less fault-tolerant JPN skipper that runs at 7.8k skips/hour.
-  Increased the auto-correction period for the JPN skipper from 500 to 1000.
-  Day skippers are furthered hardened against trapping errors.
-  Slightly adjusted timings for MultiGameFossil.
-  Numerous updates to this manual.

### 2020-08-30:
-  Fixed the category rotation option for ClothingBuyer.

### 2020-08-29:
-  Fixed a stupid bug for all date navigation programs.

### 2020-08-28:
-  Added ClothingBuyer. It’s not efficient, but it will eventually buy out an entire store.
-  When a program finishes, it will run a user-provided callback. Here you can insert code to turn on LEDs or other output pins.
-  Failure case mitigation for date-spamming.

### 2020-08-27:
-  Fixed another issue with the rollover prevention.
-  Fixed a stability issue in date-spamming.
-  Reduced binary sizes.

### 2020-08-26:
-  Fixed a bug in the new code entry.
-  Fixed the rollover prevention to not mess up the date.
-  Fixed the date-spam farmers so that they correctly roll the year for EU date format.

### 2020-08-25:
-  Added rollover prevention to AutoHostAirplane, AutoHostFriendSearch, AutoHostRolling, and AutoHostMultiGame. This will prevent the den from rolling over if left running for a very long time.
-  When starting a program, the LEDs will flash momentarily to indicate that the program has actually started running. If the LEDs don’t flash (stay on or off), it means the device did not connect properly.
-  GodEggItemDupe has a new option to forcibly detach the item before releasing the Pokémon. This is needed to allow duplication of special items like Rusted Sword/Shield.

### 2020-08-22:
-  Code entry (including FastCodeEntry) is slightly faster for codes that require multiple long traversals.
-  When starting a program, the LEDs will turn on momentarily to indicate that the program has actually started running.
-  Slightly tweaked date-spamming to improve reliability.

### 2020-08-09:
-  Added TradeBot.
-  Increased raid exit time by 1 second for all auto-hosts.

### 2020-07-31:
-  MultiGameFossil can now hop between game versions. (Sword + Shield)
-  AutoHostMultiGame will now accept FRs for the next den instead of the current one. Raiders no longer need to wait for the autohost to complete a full cycle before they see any stamps. This can be configured.
-  Add recommendation to stand behind the den/tree for WattFarmer and BerryFarmer.
-  Improved efficiency of GodEggItemDupe.
-  Minor reliability tweaks.

### 2020-07-19b:
-  AutoHostMultiGame can now hop between game versions. (Sword + Shield)
-  Tweaks to make the rolling auto-hosts less likely to kill the den.

### 2020-07-19:
-  Bug fixes and reliability improvements.

### 2020-07-15:
-  Added AutoHostMultiGame.
-  Numerous updates to this manual.

### 2020-07-14:
-  Added StowOnSideFarmer to farm the bargains dealer.
-  Added 7k skippers for US and EU date formats. These run at 7.1k and 7.5k skips/hour respectively.
-  More reliability tweaks to the day skippers.
-  All day skippers now default to 10 skips instead of 200,000. This makes it harder to overskip by using the wrong program.
-  Adjusted egg timings to improve reliability.
-  Code entry will skip invalid digits instead of converting them to zero.
-  Removed “!ReadMe.txt” since it has been superseded by this manual.
-  Removed documentation for all programs since they are now in this manual.
-  Minor grammar and wording changes to this manual.
-  Build scripts have been shuffled around.

### 2020-07-11:
-  Added this manual.

### 2020-07-10:
-  The 7k skipper should be more resistant to trapping errors.

### 2020-07-09:
-  Fixed an issue in the 7k skipper auto-correction.

### 2020-07-08:
-  Merged all 3 MCU packages into one.
-  Exposed some more den timings.

### 2020-07-04:
-  Fixed an issue in MassRelease where it wouldn't turn on the LEDs when done.

### 2020-07-03:
-  Minor timing adjustments to den rolling and auto-hosts.
-  Adjustments to game startup for MultiGameFossil.
-  Fixed the way MultiGameFossil ends.
-  EggSuperCombined now recommends turning on airplane mode to improve mass release stability.

### 2020-06-30b:
-  Fixed an issue where date-spam programs may not completely roll back the date.

### 2020-06-30:
-  WattFarmer and BerryFarmer now have an option to periodically save the game. This is disabled by default since crashes are extremely rare.

### 2020-06-29b:
-  When the 7k skipper finishes, it will go in-and-out of the date change menu every 15 seconds to prevent the time from naturally advancing past midnight thereby resulting in an extra (unintended) day skip.

### 2020-06-29:
-  The BuildAll script will now tell you which programs failed to build.
-  The BuildAll script will now delete old .hex files so you don't accidentally use old ones.
-  Minor timing adjustments to auto-hosts.
-  Month adjusting corrections have been removed from 7k the skipper. Thus it's no longer necessary to specify the real life month. The overhead for a month-adjusting correction is greater than skipping on a 30-day or even a 28-day month following a trapping error that syncs the clock.

### 2020-06-27:
-  Update LUFA library to latest. (790ac4d)

### 2020-06-26:
-  Fixed a possible compilation error in the LUFA library for Mac.
-  The 7k skipper will now blink the LEDs to indicate roughly how many skips are left. The faster it blinks, the fewer skips are left.

### 2020-06-25: 
-  The BuildAll script now tells you when it's safe to close it.
-  Yet even more timing changes to improve egg program stability post-DLC update.
-  Potential fix for GodEggItemDupe failing in French.
-  Potential fix for den rolling getting stuck in box.
-  Potential fix for den rolling not rolling back the date.
-  Experimental feature to alternate between Sword+Shield games for AutoHostRolling.

### 2020-06-22:
-  More den and auto-host timing adjustments to increase stability.

### 2020-06-21b:
-  Added FastCodeEntry. All the power to be an asshole.

### 2020-06-21:
-  Added new (slower, but more reliable) method for dodging uncatchables when den rolling. This method is disabled by default.
-  Updated instructions for the 7k Skipper to specify that the Isle of Armor Dojo is not a place that can be used to skip frames. You must be in an actual Pokémon center.

### 2020-06-19:
-  Even more timing changes to improve egg program stability post-DLC update.

### 2020-06-18:
-  Timing changes to improve the reliability of egg programs post-DLC update.
-  Timing changes to hopefully improve reliability of den rolling.
-  Auto-hosts now support partially random raid codes. This will make it much easier to enter random raid codes for streamers.

### 2020-06-17b:
-  Auto-hosting with no code now works for uncatchable Pokémon.
-  Den rolling should now work for uncatchable Pokémon.
-  Faster code entry because 8-digit codes suck.

### 2020-06-17:
-  8-digit codes for DLC update.

### 2020-06-15:
-  Added AutoHostFriendSearch.
-  The artificial delays for auto-hosts has now been fixed.
-  Updated documentation for the 7k skipper. Empirical evidence suggests it's a lot more stable than the documentation makes it sound like.

### 2020-06-13: 
-  Fixed an issue where AutoHostSleep and AutoHostAirplane will start the raid even if nobody joined.

### 2020-06-12:
-  When a program finishes, it will turn on the LEDs.
-  Further relaxed timings for mass release to improve stability.
-  Increased the default auto-correction interval for 7k skipper from 250 -> 500.

### 2020-06-09:
-  New implementations for all remaining Brianuuu programs:
  -  TurboA
  -  MassRelease
  -  LotoFarmer
  -  BerryFarmer
-  Build scripts are now parallelized.

### 2020-06-08:
-  Most program instructions have been rewritten to make them more clear.
-  AutoHostSleep and AutoHostAirplane now have a (dangerous) option to start a raid before the 3:00 timer runs out.
-  Possible fix for egg programs messing up box operations.

### 2020-06-06b:
-  Possible fix for the egg programs playing a different game.

### 2020-06-06:
-  FriendDelete now has an option to block users instead of just deleting them.
-  Soft-reset timings have been adjusted and are now configurable.
-  Den rolling timings have been adjusted to hopefully improve reliability.
-  Potential fix for auto-hosts killing dens.
-  Build scripts now save build errors to logs.
-  Build warnings will now error.
-  Minor timing changes to all date-spamming programs.

### 2020-06-04: 
-  Exposed FriendDelete timings for user configuration.
-  Potential fix for AutoHostRolling destroying dens.
-  Potential fix for DenRoller and AutoHostRolling failing the first date skip.

### 2020-06-01:
-  Add debugging option to toggle timesync after egg program ends.

### 2020-05-29: 
-  Increased box pickup/drop time to increase stability of egg programs.
-  Speculative fix for MultiGameFossil not stopping when it's supposed to.
-  Updated warnings and recommendations for all auto-hosts.

### 2020-05-27: 
-  Fixed a build issue with EventBeamFinder caused by a naming conflict.
-  Adjusted Home->Game timings to improve DenRoller and AutoHostRolling stability.

### 2020-05-26: 
-  More adjustments to EggSuperCombined mass release timings.
-  The default exit time for auto-hosts has been pushed earlier.
-  MultiGameFossil now tolerates the system update window.

### 2020-05-23: 
-  Adjusted mass release timings to increase stability of EggSuperCombined.
-  Added empirical fetch/hatch rates data for EggCombined.
-  The default for START_GAME_REQUIRES_INTERNET is now false. I have yet to see anyone play a downloaded copy of the game on a non-primary Switch.

### 2020-05-22: 
-  Tweaked den rolling timings to hopefully increase stability.
-  Exposed more den rolling timings to configuration.

### 2020-05-21: 
-  Tightened some timings in the auto-hosts.
-  Slightly relaxed timings for MultiGameFossil to improve reliability.
-  Relaxed den rolling entry timings and add an option to configure it.

### 2020-05-19: 
-  Relaxed mass release timings in EggSuperCombined to improve reliability.
-  More build script refactorings.

### 2020-05-18: 
-  New method of building. Double-click on the appropriate .cmd file instead of editing the makefile!
-  Re-added the atmega16u2 MCU because I'm stupid.
-  Fixed some settings options that broke during the refactor.

### 2020-05-17: 
-  Major refactoring of the build process.
-  Further tweaked date spamming for WattFarmer.
-  Increased box-change delay to improve stability of egg programs.

### 2020-05-16: 
-  The 4k skipper has been removed. It will be distributed in a separate package.
-  Fixed a minor issue where JPN egg hatching tolerance was always enabled.
-  Added a "Required Parameters" section to the instructions of each program to clarify what parameters need to be set properly to use the program.
-  Slightly tweaked timings for date spamming.
-  Moved a ton of box navigation timings into Settings.h so they're more easily configured.

### 2020-05-11: 
-  BeamReset now goes in-and-out of the game several times to flash the beam before it resets.
-  EventBeamFinder: Drop wishing pieces until you find an event den.
-  Added an option to make the egg programs work in Japanese.

### 2020-05-10:
-  Added MultiGameFossil (beta). Now you can revive fossils for more than 4.5 hours at a time by utilizing multiple saves!
-  BeamReset has been updated to require slow text. Apparently some Switches save extremely quickly - enough to break the program under fast text speeds.

### 2020-05-09:
-  Added BeamReset to make purple beams less painful.
-  Fixed some timings that could cause den rolling and rolling-auto-host to fail to reset the game.
-  Lot of minor timing changes.

### 2020-05-08: 
-  Added support for random raid codes to the auto-hosts.
-  Relaxed the box entry timings for all the egg programs.
-  Rolling auto-host start time no longer includes the 8 second lobby open wait. So now it starts closer to 2:00 now.

### 2020-05-06:
-  Recalibrated "TICKS_PER_SECOND" and adjusted it from 123 -> 125.
-  Fixed an issue in the egg hatchers where it can incorrectly back out all the way to the overworld on faster Switches.
-  Fixed some timings in the egg hatchers that broke after migrating the framework.
-  Fixed game entry timings when starting game requires internet.

### 2020-05-05: 
-  Moved "Settings.h" into the main folder so that it's more accessible.
-  Cleaned up "Settings.h" so that's clearer and better documented.
-  Added an option that will allow programs that soft-reset to work when starting the game requires checking the internet because the game isn't a physical cartridge and the Switch isn't the primary Switch.
-  The 7k skipper's is slightly faster again.
-  The 7k skipper's default auto-correction interval has been reduced from 500 to 250.
-  Adjusted some timings with the mass release to make it more reliable.

### 2020-05-03: (beta)
-  Slightly faster date spamming for watt farmer and den rolling.
-  Slightly modified timings for box operations in the egg programs.
-  The 7k skipper is about 1.6% faster. 

### 2020-04-29: 
-  Fixed EggHatcher which was broken by a refactoring.
-  Fixed the start-timer for AutoHostRolling to 2:00. Accidentally left it on 2:15 after hosting yesterday.
-  Added this ReadMe file.

### 2020-04-27: 
-  Lots of minor timing adjustments for all programs.
-  Another fix that hopefully fixes the no-code raids.
-  Added EggSuperCombined. Combines mass-release with EggCombined.
-  Added forbidden program GodEggItemDupe. Mass duplicate items with the God Egg.

### 2020-04-23: 
-  Relaxed the den entry timings for auto-hosting to hopefully fix the no-code problem.
-  Add warnings about messing with TV displays to all programs.
-  Updated documentation for EggCombined.

### 2020-04-21:
-  Fixed some timings with the egg programs to make them more reliable.
-  Fixed some timings with the WattFarmer to make them more reliable.
-  The WattFarmer's starting sequence is more optimized.
-  Renamed the two JPN day skippers to "DaySkipperJPN_4k" and "DaySkipperJPN_7k".
-  Slightly faster auto-correction logic for both day skippers.
-  The 7k skipper now asks for the current (real-life) month so that auto-corrections will land you back on a month with 31 days.
-  Added a global option to make the programs more tolerant of the system update window. This is disabled by default for den-rolling and auto-hosts since it affects performance.

### 2020-04-20: 
-  Added WattFarmer which is about 50% faster than Brainuuu's.
-  Den rolling is now better optimized.

### 2020-04-19: (beta)
-  Massive refactor of all programs to switch to a new controller framework.
-  The 4700 skipper has not been migrated since doing so would make it identical to the 7k skipper. For now, the public only knows (rumors) about the 4700 skipper. But they have no idea about the 7k skipper.

### 2020-04-18:
-  Refactor of a ton of code. So not a lot of functional changes.
-  Den rolling and FR-accepts are now faster.

### 2020-04-16:
-  DaySkipper_JP_Fast2: A new day skipper that runs at fucking like 7000/hour.
-  DenRoller and AutoHostRolling use a new method to roll the date.
  -  There no longer a constraint on your starting date.
  -  It rolls backwards first.
The idea here is that you'll be resetting the game on the target frame when you're done hosting that. So it's better to have your date correct at this point. In the past, if you forgot to fix the clock after rolling the den, every mon you caught would be in the future. Some of the timings for den rolling have also been tightened to make it faster.
-  New Program: AutoHostSleep - Similar to AutoHostAirplane, but it uses sleep instead of airplane mode. Thus it works while docked. But techinical limitations with the method mean that the program will wait 30 seconds before it starts hosting. Similarly, the artificial delay between raids cannot be skipped for the first raid.

### 2020-04-14:
-  EggHatcher and EggCombined now require that you have the cursor over "Pokémon" instead of the "Town Map".
-  Adjusted some timings in EggHatcher and EggCombined to improve reliability. (Rowlett was failing with EggCombined.)
-  Added SurpriseTrade: A super-dangerous program that will wonder trade entire boxes of Pokémon. :lul:
Brianuuu also dropped a new version of his Arduino programs which includes a lot of the stuff that we have here. Neither set of programs are strictly better than the other. Thus they will continue to complement each other.

### 2020-04-12: 
-  When connecting to the internet for auto-hosting, the cursor will be moved as far away as possible from the Link Trade and Surprise Trade buttons. This reduces the chances of a slow internet connection breaking the program in a way that initiates a trade.
-  Add warnings that unattended auto-hosting is not recommended due to accidental trade risk.
-  Improved documentation for all the delay parameters in the auto-hosts.

### 2020-04-11:
-  Auto-Hosts: Auto FR-accepts is now delayed by a few seconds to keep it from clipping the start of the lobby.
-  Auto-Hosts: The artificial delay between raids is suppressed for the first raid.
-  Tightened some timings for DenRoller and AutoHostRolling.*
-  EggCombined: Misc. reliability improvements.
-  EggCombined: The default # fetches/batch has been increased to 6.

### 2020-04-09: 
-  Added EggCombined. It's harder to use than EggFetcher and EggHatcher, but can be a lot more efficient.
-  Relaxed some timings in EggHatcher to make it more reliable.
-  Relaxed some more timings in the auto-hosts to improve reliability.

### 2020-04-06:
-  The FR-accepting auto-hosts have been merged into the regular ones as an optional feature. So it's back to two programs, AutoHostAirplane and AutoHostRolling.
-  The per-raid extra delay option has been added to the rolling auto-host as well. But it only make sense to use if you're hard-locked instead of rolling.
-  For the rolling auto-host, added the ability to select a 1st move. Now you can flex your hosting shiny!

### 2020-04-05:
-  Relaxed the timings of FriendDelete.
-  Add an option to the airplane auto-hosts to increase the time between raids. This makes farming more efficient when the raid cannot be cleared before the next raid starts.
-  Add FriendDelete to the makefile comments.
-  Clarified the instructions that you need to set USER_SLOT in order to pick the right account for auto FR-accepts.

### 2020-04-04:
-  Tweaked the EggHatcher incubation period equation. Should fix issue with Lapras not having enough time to hatch.
-  Add FriendDelete. Mass delete friends to clean up after auto-hosting with auto-FR accept.
The friend-deleter isn't super-well tested since it's a pain-in-the-ass to test.

### 2020-04-03:
-  Added AutoHostAirplaneFRs. Now both of the auto-hosts have automatic FR-accepting versions.
-  Minor code changes to everything.

### 2020-04-02: 
-  Added AutoHostRollingFRs: Rolling auto-host that will automatically accept friend requests.
-  Slightly tweaked timings for EggFetcher, DenRoller, and both auto-hosts.

### 2020-04-01: 
-  Loosened some timings that can sometimes cause the auto-host programs to not connect to the internet.
-  Loosened the timings for the box operations in the EggHatcher.
-  The EggHatcher now travels further to the right for added safety.
-  Speculative fix for an issue that can cause the egg programs to fail to fly back to Route 5.
-  Updated comments and instructions including some precautions.

### 2020-03-30:
-  Loosened some timings in DenRoller and the auto-hosts to make them more reliable. This helps fix some (recoverable) issues where it would fail to roll the correct # of times (and thus host the wrong frame) or will fail to enter a code.
-  The EggFetcher has been retuned. It now properly dodges the man on the bridge and has a higher chance of successfully fetching an egg on each fly-back.
-  EggHatcher timings have been updated to make it more reliable.

### 2020-03-29:
-  EggHatcher now uses the spinning method. I strongly recommend that you stay offline. One of the failure cases may result in it entering YCOMM and starting a trade.

### 2020-03-28b: 
-  In the JPN skipper, the default auto-recovery period has been increased to 200 skips.
-  Some refactoring of all the progs.
-  Added EggFetcher and EggHatcher.

### 2020-03-27: 
-  Fixed a bug where 0s in the code for auto-host might not work.
-  Added airplane auto-hosting for soft-locks.
-  Tweaked timings for various things.

### 2020-03-26: 
-  Fixed a bug in the DaySkipper_JP_Fast where it didn't count days properly.
-  Adjusted the timings for AutoHostRolling to make it more reliable.
-  AutoHostRolling will now button mash A from start of raid to when it closes the game. This gives about ~10 seconds of leeway for people to be late without killing the raid.

### First Release: 
-  DaySkipper_JP_Fast: A faster JPN skipper that runs up to 4700/hour.
-  DenRoller: A more generic den roller that rolls N days instead of 3.
-  AutoHostRolling: Roll N days, host raid, reset. Repeat.