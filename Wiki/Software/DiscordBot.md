# Discord Bot Integration:

**Back To:** [Discord Integration](DiscordIntegration.md)


This section covers how to set up and configure a Discord bot.

Discord bot integration can be useful for various things. For example:
1. Get notified when a shiny is found.
2. Get notified when a long-running program is finished or otherwise needs your attention.
3. Send notifications for live (real-time) hosting.
4. Use remote control commands to start or stop a program, send controller inputs, take screenshots, etc.

<img src="images/discord-notifications-0.png">



## Step 1: Create and set up your Discord bot application

1. Go to [Discord's Developer Portal](https://discord.com/developers/applications) and create a new application.

2. Navigate to the Bot tab and add a new bot. You can give it a username and an avatar if you wish. This is the tab you will get your bot token from, we'll need it later.

	***Important note: never share or reveal your token to anyone. If you do, other people will be able to access your bot account and abuse it.***

3. Make sure your bot is set to private, otherwise anyone will be able to invite it to their servers.

<img src="images/discord-bot-private.png">

4. Under Privileged Gateway Intents enable `Presence Intent`, `Server Members Intent`, and `Message Content Intent`. Save your changes.

<img src="images/discord-bot-intents.png">

5. Now head to the OAuth2 tab and click URL Generator; we need to generate an invite URL with the correct permissions. Select `bot` under scopes. You now have two options:

	a. Grant `Send Messages`, `Embed Links`, `Attach Files`, `Read Message History` permissions. Copy the generated URL below and paste it into your browser of choice. This will allow you to invite the bot to a server you have Manage Server permissions in, and your bot will have a pre-configured role.

	b. Do not grant any permissions, copy the generated URL below and invite the bot to a server you have Manage Server permissions in. Bot will not have any permissions, you can configure a role in the server. **This is the preferred option if you are setting up your bot in someone else's server.**

<img src="images/discord-bot-permissions.png">


## Step 2: Open up the Discord settings.

Open up the serial programs and click on the Settings button in the bottom-left section. This opens up the settings panel. Scroll down to the Discord settings. Enable `Discord Integration Settings`.

**Settings overview**

* **`Discord token`**: This is where you'll paste your bot's token. It will be blanked so you don't accidentally reveal it.
* **`Discord command prefix`**: Symbol or text your bot will recognize as the start of a command.
* **`Discord bot use suffix`**: If enabled the prefix will be matched at the end of a command.
* **`Discord game status`**: Flavor text that will appear under your bot's status in a server sidebar.
* **`Discord hello message`**: Bot's response to the `$hi` command. If you enter `<!>` in your custom message, the bot will ping whoever invoked this command.
* **`Discord sudo`**: Enter comma-separated user IDs you wish to grant remote button click command access to.
* **`Discord owner`**: Enter your own user ID. This will also enable sudo commands.

<img src="images/discord-bot-program-settings.png">


## Step 3: Get your Discord bot's token and your user ID.

1. Your Discord ID is not "Username#1234". It's actually just a number. To get your Discord ID, [follow this guide](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID-).
Paste your ID into the `Discord User ID` and `Discord owner` boxes.

2. If you haven't already, head back to the Bot tab in Discord's Developer Portal, reveal and copy your bot's token. Then paste it into the `Discord token` box.


## Step 4: Set up your channels and notifications.

1. Click "Add Row". In the `Description` box enter your own description so it's easier for you to identify channels later on.

2. Similarly to how you got your user ID, get the channel ID you want to send notifications to and enter it.

3. If you want your bot to respond to commands in that channel, check `Allow Commands`.

<img src="images/discord-notifications-program-settings-bots-0.png">


## Step 5: Send a test message and try out commands.

Click `Start Bot`. If channel permissions are configured properly, the bot should appear online after a few moments. If it doesn't, check the channel and role permissions.

If the bot is online, good job! Now let's test notifications and commands!


Navigate to any program that sends notifications. All programs that send notifications will have the following section near the bottom of the settings.

<img src="images/discord-notifications-event-settings-0.png">

Click on any of the "Send Test Message" buttons. If everything worked properly, this will send a message to the configured channel(s).

<img src="images/discord-notifications-bot-0.png">

If it doesn't, there can literally be a million things wrong. A good place to start is to open up the Output Window and look for any errors.

***

# Expanded Settings Overview

### Column: "Description"

Enter your own description for each channel so you can identify them more easily.

### Column: "Allow Pings"

If unchecked, you will never be pinged by the bot. If checked, you will be pinged if the notification requests a ping.

In order to be pinged by a notification, all of these conditions must be met:
1. The notification is sent to your bot.
2. "Allow Pings" is checked.
3. "Should Ping" is checked for the respective event in the program's discord notification settings.

### Column: "Event Tags"

This lets you filter what events are sent. A notification is only sent if a tag is shared with the event itself.

A notification is sent only if all of these conditions are met:
1. The bot is started and `Enabled` is checked for a given row in Discord settings.
2. The corresponding event in the program is enabled. (Notifications are enabled for the program and "Enable" is checked for the respective event.)
3. There is at least one tag in common between the channel and the event type in the program.
4. The event that is being sent is not being rate limited.

The tag can be any alpha-numeric string and must match exactly. By default the program pre-populates the tags with "Notifs", "Showcase", and "LiveHost". You are free to change them or make your own.

A typical use-case is to send logs ("Notifs") down one channel while broadcasting live-hosting notifications to multiple servers.

### Column: "Allow Commands"

This lets you toggle whether your bot will respond to commands in a given channel.

### Column: "Channel ID"

This lets you specify and fine-tune channels for notifications and commands.

***

## Command Overview

A general command cheat sheet.

## Miscellaneous Commands

* **`help`**: Will post all commands that are available to the invoking user with their parameters.
* **`botinfo`**: Will post information about currently running programs and consoles. Good way to find out your console ID (required as a parameter for some commands).
* **`about`** Will provide some general information about the bot.
* **`hi`**: Will post a cute response to the command invoker.
* **`ping`**: Will post a latency estimate (bot will post a message and edit it with the delay between server responses).

## Sudo Commands

* **`click <console id> <button> <hold ticks>`**: Will send a button input command to the specified console.
* **`leftstick <console id> <x position (0-255)> <y position (0-255)> <hold ticks>`**: Will hold the left joystick for the specified console for a time.
* **`rightstick <console id> <x position (0-255)> <y position (0-255)> <hold ticks>`**: Will hold the right joystick for the specified console for a time.
***Note: if a program is running, remote button commands will be denied. Remotely stop a running program first.***

## Owner Commands

* **`start <console id>`**: Will start a stopped program for the specified console.
* **`stop <console id>`**: Will stop a running program for the specified console.
* **`resetserial <console id>`**: Will reset the serial connection for the specified console.
* **`resetcamera <console id>`**: Will reset the camera view for the specified console.
* **`screenshot <console id> <format (png or jpg)>`**: Will take a screenshot from the specified console and upload it to the channel this command was invoked in.
* **`reloadsettings`**: Will reload Discord settings.
* **`shutdown`**: Will (ungracefully) terminate the entire program. Best to avoid using it, settings and stats will not be saved.


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)






