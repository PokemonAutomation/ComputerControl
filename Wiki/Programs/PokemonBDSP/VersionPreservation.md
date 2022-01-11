# Version Preservation

**Update 2021/12/21:**

This page was originally written when v1.1.2 was released patching out the original menu glitch. Since then, a new way to menu glitch was found on v1.1.2 which was subsequently patched out on v1.1.3.

This cat-and-mouse game of increasing version numbers doesn't change the validity of anything on this page.

This article will assume that v1.1.1 is the desired game version and v1.1.2 is the bad game version.

-----

If you're here, you probably already know that Pokémon BDSP has a number cloning exploits. Two of which have been automated:

- [Clone Items (Menu Overlap Method)](CloneItemsMenuOverlap.md)
- [Clone Items (Box Copy Method)](CloneItemsBoxCopy.md)

These exploits have been patched in v1.1.2 - thus making it one of the "bad" game updates because it removes the *useful* bugs, while leaving behind all the *bad* ones.
(Namely, v1.1.2 patched all the cloning glitches, while leaving behind all the broken PokeRadar and shiny charm mechanics.)

Thus it is better to stay on v1.1.1 unless you need to go online.

This page will give a summary on the different ways to keep v1.1.1 or downgrading the game version in general.
All methods here can be done with normal Switches and do not require CFW or homebrew. But they will require:

1. A physical game cart (not digital)
2. A minimum of 2 Switches (ideally 3).
3. A Switch that has the game version which you wish to preserve. In other words, you must have at least one Switch that has not been updated to 1.1.2.


## Anti-Downgrade Mechanisms

The Switch (and many other platforms) *really* want to keep you on the latest version of everything and will go out of their way to prevent you from downgrading anything.
The most extreme example of this are the [firmware fuses](https://blog.jonlu.ca/posts/nintendo-switch) - which fortunately does not apply to game versions.

As such, Nintendo makes it very difficult to downgrade a game version. And if you are not on the latest version, it keeps nagging you until you update or you fat-finger the update button.
Likewise, you cannot go online in the game unless it is fully updated to the latest version.

Once a game has been updated to a specific version, the Switch "remembers" which game version it had and will refuse to run an earlier version even if you wipe the game from the Switch. The only way is to factory-reset the Switch. (see [Downgrading](#downgrading))

This extremely user unfriendly process is quite intentional by design. Because as we said, they want to force everything to the latest version.


## Avoiding Game Updates

The most important part to staying on an old game version is to avoid the updating to the latest.

**Disable Automatic Game Updates:**

This is the most important and is basically required for any attempt to stay at an older version to work. This can be done in the Switch settings all the way at the bottom.

**Stay Offline:**

Staying offline isn't always feasible, but is worth mentioning anyway. And it only works if the Switch doesn't know there is an update for the game.
Once you start seeing the game update prompt, it is too late. The moment, you click "update" (either intentionally or not), you will be blocked from playing the game until it updates.

**Airplane Mode:**

If the Switch knows there is a new update, run all programs in airplane mode if possible. Should something go wrong and the program accidentally starts the update, airplane mode will block the update until you return. Then you can [recover the old version.](#syncing-game-version-with-another-switch)


**Configure Programs to Avoid the Update Window:**

Most of the programs in this project that navigate between the game and the Switch settings will inevitably encounter any game or system update menus.
Unexpected updates will usually break the running program because the program will trigger the update and restart the Switch. This is especially bad for CFW since they need to hold off firmware updates until the custon firmware itself is updated to support it.

To counteract this, there are two options in `Switch -> Framework Settings` that allow the programs to avoid the update menu by inserting an UP+A press.

- [`Tolerate System Update Menu (fast)`](../NintendoSwitch/FrameworkSettings.md#tolerate-system-update-menu-fast)
- [`Tolerate System Update Menu (slow)`](../NintendoSwitch/FrameworkSettings.md#tolerate-system-update-menu-slow)

The "fast" one is enabled by default. Most programs use this. The "slow" one is disabled by default and is used only by programs that are significantly slowed down by the update menu. (Sword/Shield den programs)

If the relevant one is enabled for a program it will be able to dodge either a game update or a system update menu. But it cannot dodge both at the same time.

However, it will not be able to dodge a game update menu if starting the game requires checking the internet. (if the game is digital and the Switch is non-primary)


## Syncing Game Version with another Switch

It's impossible to update to something that isn't the latest version online. But fortunately, the Switch allows you to synchronize game versions across 2 (or more) Switches locally without an internet connection.
This can be utilized to update another Switch to a version that isn't the latest. However, it cannot be used to *downgrade* a version.

To upgrade a Switch locally, you need:

- A Switch with the desired game version.
- The Switch you wish to *update* to the desired game version. If it has a newer game version, you will first need to [downgrade](#downgrading) it.

Thus you need at least 2 Switches. If your goal is to synchronize BDSP v1.1.1, you need to have at least one Switch that is currently on v1.1.1 and has not been updated past that where the exploits are patched.

**Instructions:**

1. On both Switches select the game you with to synchronize in the Switch home and press `+`.
2. Go into `Software Update` -> `Match Version with Local Users`.
3. Select the host to be the Switch with the v1.1.1 (or whatever version you wish to sync to).

This will update the Switch that is behind to the Switch that has the latest version. ***Do not do this if either Switch is already on 1.1.2 as it will update the other one to 1.1.2 instead.***

**(Note: This will also update the Switch firmware if that is behind.)**


## Canceling an In-Progress Update

As is often happens, when playing manually (or automated with a misconfiguration), you will accidentally initiate a game update. In other words, "fat-fingering". Unfortunately, you cannot stop the update once it has started.

But there is one (ugly) work-around. Delete the game entirely.

**Instructions:**

1. Press `+` on the game.
2. Remove the game cartridge from the Switch.
3. Select `Manage Software` -> `Delete Software`. This will delete the game without deleting the save files.
4. Insert the game cartridge back into the Switch to make the game reappear.
5. [Synchronize with another Switch that has the game version you want.](#syncing-game-version-with-another-switch)

Thus the importance of having a backup Switch that holds game version that you want to keep.


## Downgrading

What if you already updated to 1.1.2? Now your options are much more limited and the methods get very ugly.

As menitoned earlier, the Switch remembers the version numbers of every game that has ever been on it. If you ever try to start a game with an earlier version, it flat out refuses to run without updating.

*There is only one known way to fix this (without hacking the Switch * ): **Factory Reset***

This needs to be a complete factory reset that wipes all user data as well. The "reset" that preserves user data does not reset the game versions that it "remembers".

*Thus, you need to transfer all your save files and settings to a spare Switch or else you will lose it from the reset.*

Once you have reset the Switch, you can insert the game cartridge back into it and [synchronize it back to the version you want.](#syncing-game-version-with-another-switch)

If you do not have a Switch that you can utilize to synchronize to the earlier version, you are unfortunately stuck with the version that's on the game cartridge itself.

(* *Even if you have a hacked Switch, don't do this using any method not available to non-hacked Switches unless you're completely offline in emuNAND. Since you'll probably just get your Switch banned.*)


**Important Note:**

If you have saved a game on version 1.1.2 (or any version that's *later* than the one you want to roll back to), you are stuck.

Save files are not backwards compatible so you will not be able to load a save file that was last saved using a later version of the game. This is enforced by the Switch system itself.

If you transfer a save with with a newer game version to a Switch that only has the older version, that Switch will know of the new game version and will block you from starting the game until it is updated. Again the only way to undo this is to factory reset the Switch.


## Preparation Steps

All the information above may be too much to digest. But here are some general preparation and usage steps.

### Preserving an older Game Version:

1. Do not update the game on all your Switches. Keep at least one Switch at the game version you want (v1.1.1).
2. Designate an (ideally offline) Switch to storing the older game version as a backup.

If you have both game version (Brilliant Diamond and Shining Pearl), you will want to do this for both. But of course they can share the same backup Switch.

### Effectively Cloning in the Patched World:

Since downgrading is difficult and save files are backwards incompatible, there really is only one way to mass clone and still reap the benefits in the latest game versions that can go online. Namely - one way transfer.

The idea here is to build yourself a collection of valuable items/Pokémon in an unpatched version (v1.1.1 or earlier). Transfer a clone of them into a throwaway save file, mass clone them there, then update the save file to the latest where they can be transferred to your main (fully updated) saves.

**Example:**

You have 3 Switches:

- Switch A is on the latest (v1.1.2) and can go online. This has your main save file that you play online.
- Switch B is on v1.1.1 and has internet access.
- Switch C is an offline backup that stores v1.1.1.

Then the workflow is:

1. Start a game on Switch C and collect one of every valuable item. This will need to be done offline if you don't already have them. This will be your "master" copy to spawn clones.
2. Start a new "transfer" game on Switch B and play far enough to get the box link. (1 badge)
3. Catch/clone a bunch of Pokémon in the new transfer game.
4. Clone a copy of your valuable items on Switch C.
5. Trade that copy into your transfer game on Switch B. (A mass trading program is coming in the near future.)
6. On the transfer game in Switch B, mass clone the items using item cloning programs.
7. Upgrade Switch B to the latest game version.
8. Mass trade the items from the transfer game into the main save. (again, mass trading program is expected in the future)
9. [Factory reset Switch B to downgrade it.](#downgrading)
10. [Synchronize game version](#syncing-game-version-with-another-switch) v1.1.1 from Switch C to Switch B.

This can be done as many times as you want by repeating steps 2 - 10.

If you have both game versions (BD+SP), you can actually do this with only 2 Switches at the cost of losing fat-finger protection.
Since both Switches will be online, it will be very easy to accidentally update your only copy of v1.1.1 to the latest.


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

