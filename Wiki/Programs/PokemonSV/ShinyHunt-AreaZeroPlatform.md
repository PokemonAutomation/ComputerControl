# Shiny Hunt - Area Zero Platform

*This program is still in development and it not yet available to the public.*

<img src="images/ShinyHunt-AreaZeroPlatform-0.png">

(Image shamelessly stolen from Scotteh's run of the program.)


## Program Description

This program will shiny hunt the specific platform detailed in this video: https://youtu.be/5NeLVaE7t8c?t=274

While that video is focused on the idling the ghost exploit for Flutter Mane, the same platform can be used to shiny hunt almost everything else there.

In particular, this program can be used to shiny hunt all of these paradox Pokémon:

- Great Tusk
- Scream Tail
- Brute Bonnet
- Flutter Mane
- Iron Treads
- Iron Bundle
- Iron Hands
- Iron Jugulis
- Iron Valiant (requires sandwich)

This program works by standing on an inside edge of the platform and sending out your lead for Let's Go to kill everything in sight. Because Let's Go auto-battle does not attack shinies, shinies will remain and (with fairly high probability) will wander close enough to your character to trigger an encounter. While the program cannot detect shinies in the overworld, it can hear them during an encounter.

Since the program cannot see shinies in the overworld, it will not immediately try to engage them when they spawn. So there is a chance that a shiny will despawn (Dunsparce) or fall off the platform. Our statistics suggest around 30% of shinies are lost this way. But that's an acceptable cost of automating.

Making a sandwich before running this program will drastically increase shiny rates and better target what you are hunting for. But since sandwiches only last 30 minutes, it's no longer full automation. Automating the sandwich making for a generic sandwich is a daunting task which we will attempt in the future.

Like the encounter bots from Sword/Shield and BDSP, this encounter bot supports auto-catching by blindly throwing balls. But due to the low catch rates of paradox Pokémon, you will need a very tanky lead and a lot of balls.

<img src="images/ShinyHunt-AreaZeroPlatform-2.png">

### Setup of Settings

1. Text Speed: Fast
2. Skip Move Learning: On
3. Give Nicknames: Off


### Instructions

1. Make sure your party is full.
2. Your lead Pokémon is fast and capable of defeating everything without taking damage.
3. Your lead Pokémon is unaffected by Dugtrio's Arena Trap.
4. You have plenty of potions for auto-healing.
5. You have plenty of balls for auto-catching.
6. You are zoomed out to maximize your view.
7. Start the program anywhere on the platform in the overworld with all menus closed.

The best known Pokémon for a lead is Corviknight that is level 100, defensively trained, and holding leftovers. Miraidon and Lucario will work if given a Smoke Ball. However, the lack of leftovers for self-healing makes them less suitable for auto-catching.


## Options

<img src="images/ShinyHunt-AreaZeroPlatform-3.png">

### Game Language:

This is the language of your game and is required to read the names of what you encounter. Thus this is also required for auto-catch to work.

### Mode:

Start the game either on the platform or just inside the Zero Gate station.

### Actions Table:

By default, the program will run from non-shinies and stop on shinies. Here you can specify an action for different encounter types by Pokémon name and shininess. This will let you auto-catch Pokémon in your desired ball type.

**Warning:** Level 60 Garganacl knows Explosion. Don't try to auto-catch them unless you don't mind losing some.

### Video Capture:

Take a video of the encounter if the program detects a shiny.

### Go Home when Done:

If the programs stops for whatever intended reason (a shiny, or explicit stop condition), go to the Switch Home to freeze the game. This is useful for preserving remaining sandwich time.

### Auto-Heal %:

Auto-heal your lead if its HP drops below a certain point. This will obviously consume items from your inventory.

### Platform Reset Conditions:

A platform reset is when you fly to Zero Gate, then return to the platform. This is usually done to recover from falling off the platform or to reset the spawns on the platform.

The reason for resetting spawns is that over time, the Pokémon can spawn in inaccessible places. When there are too few spawns, the kill and encounter rtes will drop to very inefficient levels. Resetting will fix this, at the cost of also despawning any shinies that have not yet been encountered.

The suboptions here are:

- Time Window
- Kills in Window
- Encounters in Window

The idea here is that there are fewer then X kills and Y encounters in the last Z minutes, then perform a platform reset. Time spent in battles and other non-productive processes are not counted towards the time window. So if you get stuck auto-catching something for 10 minutes causing your 10 minute time window to have few or no kills/encounters, the program will know to ignore that and not reset.

### Navigate to Platform Settings:

These settings govern how the program navigates from Zero Gate to the platform during a platform reset. You shouldn't need to touch anything here.



## Credits

- **Author:** Kuroneko/Mysticial


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

