# Nintendo Switch 2 Support

Nintendo launched the Switch 2 in June 2025 and it completely turned this project upside down.
Nevertheless, we are in the process of fixing the project to work on Switch 2.

In the meantime, here are some notes regarding Switch 2 automation that will differ from Switch 1.

## General Setup Requirements

This is the tl;dr if you just want to know what settings to use for Switch 2.

**Common Settings:**
- Switch menu theme must be either light or dark theme.
- Colors should be normal, not greyscale or inverted.
- Text size should be normal. Not large.

**Other Settings:**
- For programs that reset the game, you must move the user profile to the 1st one (left-most slot).
- Some programs require specifying the Switch type. (Switch 1, Switch 2 international, Switch 2 Japan-locked)


## Switch 1 -> Switch 2 Differences


### Resetting a game moves the cursor to the 1st user profile.

This is perhaps the biggest (and annoying) functional difference between Switch 1 and Switch 2.

- On the Switch 1, when you close and relaunch a game, the cursor stays on the same user profile that was previous playing.
- On the Switch 2, the cursor always moves to the 1st (left-most) user profile.

This breaks all programs that reset in-place unless the profile being used is already the 1st one.
Therefore, if you want to run a program that resets, you need to move the profile to the 1st one.

We are currently exploring ways to detect the running profile and automatically relaunch the same one.


### Japan region-locked Switches have different settings.

<img src="images/Switch2Menu-International.png" width="400">
<img src="images/Switch2Menu-JapanLocked.png" width="400">

In the regular (international) Switch 2, there are options to set the Switch language and region.
However, these settings are missing in the Japan region-locked Switch 2s.

This affects programs that manipulate the date. Thus the program needs to know what Switch you have.

There are 3 different Switch setting layouts:
- Switch 1 (original and OLED have the same layouts)
- Switch 2: international
- Switch 2: Japan region-locked

Most programs can automatically detect which layout it is. But not always.
In cases where it fails, you will need to manually specify the Switch type in the dropdown.

Programs will stop and notify you in the following circumstances:
- You do not set the Switch type, the program needs to know and is unable to detect.
- You are not specific enough with the Switch type selection, the program needs to know and is unable to detect.
- Your selection conflicts with what the program has detected.



### ESP32 wireless is currently broken.

As of today, our ESP32 wireless controllers fail to connect to the Switch 2. Even though they implement the Switch 1 wireless controller protocol, they don't do it well enough. So the Switch 2 rejects them.

As of this writing, we do not yet know how to fix this. Many other controller emulation projects are broken in the same way. So we will be keeping a close eye on them to see how they adapt and fix the issue.

Until this is fixed, the only option to connect to the Switch 2 is using wired controllers (ESP32-S3, Arduino/Teensy).



<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

