# How to Report Bugs for Computer-Controlled Programs

If you find a bug that you would like to report to developers, please prepare the following data before reporting:

## Double Check Program Wiki

First of all, double check the program wiki listed [here](../Programs/README.md) to make sure you use the program as intended: you set the correct in-game setting and program options.

## Program Options

If you think the bug is related to some program options, e.g. you set one program option to auto-save the game but the program failed to do so, please report all the related program options you use when the bug happened.

## General Information

Report the automation program version (like v0.24.8) and the name of the program that has bug.

Report when you started the program and when the bug happened.

Report your OS platform (like Win11) and your machine specs (what CPU, how many cores, memory and so on).

Report your capture card model (like Mirabox USB3.0 HDMI Video Capture Card) and how your capture card is connected to the computer.
Some of the programs rely on a very stable capture card video stream. A capture card may have not enough power or bandwidth if it is connected via a USB hub and the hub has no external power or has too many other devices connected. It this is the case, first try connecting the capture card directly to your computer's USB port and see if the bug still appears.

## Program Runtime Resource Usages

Some programs require fast video streaming and visual inferences. They may fail if the computer is too slow.

If it is likely a visual detection failure and you know your machine is not fast, please report how many CPU cores are busy and how much memory used by the program when the bug happened.

The program also shows stats including video stream FPS and video pivot utilization on top right corner of the video stream view, when the "Stats" checkbox is selected.
Please also report those stats when the bug happened.

If the computer is powerful enough, you will see video FPS to be stable 30 or 60 FPS and video pivot utilization below 10%, shown in white. If the computer is not fast enough, FPS may sometimes slow down to 20-25 FPS and video pivot utilization may be higher than 50%, shown in yellow or even red.

Usually a bug is found when the program already stopped. If you can, re-run the program, monitor the above resource usages until the bug appears, and report the usages. If the bug does not appear every time or it takes a very long time for it to occur, you can instead report the resource usages when the program runs into the stage where the bug may appear.

If your FPS is below 25 FPS, first try increasing the FPS to be at least 30. You can try closing other computer software that may occupy resources. Try connecting the capture card directly to your computer's USB port so that it has enough power and bandwidth. If you have another capture card, try using the other one. If you have a more powerful computer, try running on it. See if the bug still appears after you get a good FPS.


## Program Logs

Program logs are very helpful for developers to debug a program.

### Get Logs From Log Window

When running the program, you can click the "Output Window" button to display the log window.
This window shows all the logs from the current program session. If you close and reopen the program, you won't see any past logs from the log window.
When a bug happens, if the program is not closed, you can copy paste the logs from the log window and post them into Discord.
Note that the logs may be very long and spammy. Make sure you copy paste a long enough section of logs to be useful for debugging. Most log lines start with a timestamp:

```
2022-12-20 03:14:45.054103 - [Console 0]: Sending: pbf_press_dpad() - seqnum = 39118, dpad = 0(DPAD_UP), hold_ticks = 20, release_ticks = 30
2022-12-20 03:14:45.461269 - [Console 0]: Cursor moved.
2022-12-20 03:14:45.565994 - [Console 0]: EggPartyColumnWatcher: Count = 3, Mean = 0.332333 ms, Stddev = 0.0282902 ms, Min = 0.301 ms, Max = 0.356 ms
2022-12-20 03:14:45.566594 - [Console 0]: Saving failed inference image to: ErrorDumps/20221220-031445566588-NonEggPokemonInParty.png
2022-12-20 03:14:45.621560 - [Console 0]: OperationFailedException: check_only_eggs_in_party: Found non-egg pokemon in party
2022-12-20 03:14:45.621707 - [Console 0]: Sending: pbf_press_button() - seqnum = 39120, button = 8192( BUTTON_CAPTURE ), hold_ticks = 250, release_ticks = 250
2022-12-20 03:14:49.618579 - [Program]: Found an error before we can save the game to protect the newly kept pokemon.
2022-12-20 03:14:49.619437 - [Program]: Program stopped with an exception!
2022-12-20 03:14:49.619529 - [Program]: EventNotification(Program Error (Fatal)): Notifications not enabled.
2022-12-20 03:14:49.619548 - [Program]: Saving historical stats...
2022-12-20 03:14:49.620385 - [Program]: Stats successfully saved!
2022-12-20 03:14:49.620418 - [Program]: Program State: STOPPED
```

You can use the timestamps to know when the bug happened.
In the above logs, the program first found sth. wrong at 03:14:45, 2022-12-20 and saved a debug image in "ErrorDumps" folder.
Later it decided to report this as an error at 03:14:49 and stopped the program at same time.

You can go back enough time (like 5 min.) to get the logs starting at about 03:09:00 and copy paste the logs between 03:09:00 and 03:15:00 into Discord.

### Get Logs From Log File

If you cannot get the logs from the log window due to the program was closed or crashed beforehand, 
you can find all your past logs in a file called "SerialPrograms.log" in the folder where you launch the program.

The whole log file may be large. It could be as large as several hundred MBs!
If the whole log file is relatively small, you can upload the whole log file. Otherwise, isolate the lines that illustrate the problem you are facing.
See the above [**Get Logs From Log Window** section](#get-logs-from-log-window) on how to isolate log lines.
You can open and view the log file with any text editor. For large log files, it may wait for a while to load the entire file.


## Screenshots

Screenshots are useful for developers to test visual detection code. In the example logs in the **Program Logs** section above you can find a log line

```
2022-12-20 03:14:45.566594 - [Console 0]: Saving failed inference image to: ErrorDumps/20221220-031445566588-NonEggPokemonInParty.png
```

This log tells you the program saved a debug image in "ErrorDumps" folder.
You can find debug images like this in "ErrorDumps" folder and post it into Discord.
The name of the image contains the timestamp when it is saved. In the above example, it is 2022-12-20, 03:14:45.
So you can also use the timestamps to find the debug images without the need to look into the logs.

If the program did not save a debug image in "ErrorDumps" folder, you can still use the "Screenshot" button on the program to take a screenshot manually at the screen where the program stopped. The screenshot is saved in the same folder where you launch the program. The file name starts with "screenshot-".

NOTE: DON'T use your OS screen capture functionality or other screenshot software.
Screenshots from those are not aligned with the exact shape of the Switch screen and therefore cannot be used for the test code.

NOTE: we need the screenshot captured via the program, not via the image file transferred from the Switch after you took it using Switch's screenshot functionality, because the former is what the program sees from the capture card.

## Video (Optional)

If you happened to be recording your computer screen when the program was running, you can also post the video into Discord.
Otherwise, if you can, re-run the program with screen recording to capture the bug. A common screen recording software is OBS.
Make sure the recorded view includes both the program video stream and the log window so that we can match the log content with the video.

NOTE: make sure you have enough disk space to store the saved video stream and your computer is powerful enough so that it can process video recording while also running the automation program.

## Other info

Please include all the other details that you think can be helpful.
For example, past program usages: "I used the old version of the program for the past week and it worked fine. But after I started using the newest version, it failed. The old version is v0.24.8, the new version is v0.25.9"

## Submit to Our Discord Server

After collecting the above data, please go to [our Discord server](https://discord.gg/cQ4gWxN) and make a post under **arduino-help** forum area, inside **ARDUINO/MICROCONTROLLER** section.

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)