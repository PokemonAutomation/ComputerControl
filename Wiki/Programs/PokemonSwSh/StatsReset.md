# Stats Reset

## Program Description

Reset gift Pokémon for desired stats.

You can't shiny-hunt these, so you might as well go for stats...

<img src="https://github.com/PokemonAutomation/SwSh-Arduino/raw/master/Documentation/SerialPrograms/images/StatsReset.png" width="1000">

### Setup of Settings

1. Screen size: Must be 100% within the Switch settings
2. Video Resolution: 1280 x 720 or higher in program settings
   > Shiny detection is not reliable at low resolutions.
3. Test Speed: Fast
4. Casual mode: Off
5. Setup of menu icons are in their default locations
   1. The Pokémon option must be in the 1st row, 2nd from the left.
6. Navigate to the Pokémon PC and press "+" until the IVs of the Pokémon in your boxes are shown
   1. You need to have unlocked the IV judge for this functionality

### Party and Box Setup

1. Party Setup: Your party is full.
2. Box Setup: The first slot (upper-left) in your current box is empty.

### Instructions

1. Stand in front of the person who gives you the gift Pokémon. (or in front of Poipole)
2. Save.
3. Return to the overworld. (not inside the menu)
4. Start the program in the [Change Grip/Order Menu](https://github.com/PokemonAutomation/SwSh-Arduino/wiki/Appendix:-ChangeGripOrderMenu).

### Default Program Settings

This program requires you to input what stat range you want to search for.

***

### Options

## Options:

This program uses [`TOLERATE_SYSTEM_UPDATE_MENU_FAST`](https://github.com/PokemonAutomation/SwSh-Arduino/wiki/Appendix:-GlobalSettings#tolerate-system-update-menu-fast) to bypass the system update window.

### Go Home when Done:

After finding a match, go to the Switch Home to idle. Turn this off for unattended streaming so that your viewers can see the shiny.

### Game Language:

Set this to the language of your game. (not your Switch) This is needed for text recognition.

### Gift Pokémon:

The Pokémon you are resetting for.

### Stats:

The desired IV spread for each stat.

***

### Video Feedback:

**This program requires video feedback.**
