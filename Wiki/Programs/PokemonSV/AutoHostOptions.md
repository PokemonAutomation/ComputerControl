# Auto-Host Settings

These are settings that are used by all the Tera auto-hosting programs.

Programs that use these include:

- [Auto-Host](AutoHost.md)
- [Tera Multi-Farmer](TeraMultiFarmer.md)



## Options


### Lobby Wait Delay (in seconds):

Wait this long before starting raid. Start time is 3 minutes minus this number.

If not everyone is ready, the program will wait until everyone is ready even if it goes beyond this time limit.


### Start Players:

Start the raid when this many players have joined including the host(s). Again, it will wait until everyone who has joined is ready.


### Description:

A custom message to be put on the notification posts when a raid goes up.

### Remote Kill Switch:

Allow someone to remotely stop your auto-host. This is a URL that points to a JSON file specifying a stop time and reason. If the auto-host session crosses the time in this URL, it will stop your auto-host.

The main use-case for this is to automatically stop the auto-host before the Tera event changes. This is because Tera event changes will rollover (and kill) all raids. If stopped by kill switch, you can reset and catch your own raid instead of letting it die automatically from the event change.

The default URL is maintained by the developers of this project.

### Consecutive Failure Stop/Pause:

Pause or stop the program if this many consecutive raids fail. This is set to 3 by default since 3 consecutive improper disconnects will lead to a soft-ban from online.

### Failure Pause Time (in minutes):

If you trigger the above by failing too many times, pause for this many minutes before resuming the program. This can be used to wait out temporary internet issues.

### Rollover Prevention:

Periodically set the time back to 12AM to prevent the date from rolling over and losing the raid.

### Bans:

Ban people from your raid. If a banned person tries to join, the raid will be reset to kick them out.

Bans can be specified both via a local table of names as well as an online ban list. The online ban list can be managed by someone else.

The default URL is the shared ban list for the Pokémon Automation (PA) and Shiny Hunter Anonymous (SHA) discord servers. (These are the two servers that are closely affiliated with this project and are were the majority of the users of these programs are concentrated in.)

### Join Reports:

Track how many times each IGN has joined and generate a report. This can be used to help identify people who join too many times for the purpose of banning.

Note that these reports should not be taken as-is. Many players share the same IGN and text recognition is unreliable. So these reports should not be used for the purpose of automatic banning.


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)







