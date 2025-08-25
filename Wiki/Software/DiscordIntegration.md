# Discord Integration:

The Computer-Programs application can integrate with Discord. These can be useful for various things:

1. Get notified when a shiny is found.
2. Get notified when a long-running program is finished or otherwise needs your attention.
3. Send notifications for live (real-time) hosting.
4. Remotely control your Switch via Discord bot commands.
5. Remotely start/stop programs via Discord bot commands.

<img src="images/discord-notifications-0.png" height="600">


**Sub-Articles:**
- [Discord Webhook Notifications](DiscordWebhooks.md)
- [Discord Bot Integration](DiscordBot.md)

# Bot vs Webhook
When setting up Discord integration, you have the option of setting up a bot or a webhook. Both can send notifications, but do so differently.

A webhook is a URL. You (or anyone else that knows the URL) can make a POST request to that URL and then Discord will send the contents of that request as a message in the webhook's channel. This is all that webhooks can do. They can do nothing else except send a message in one specific channel. Webhooks are not restricted by permissions; making a valid request to the hook will always result in a message, there's no way to prevent that.

Bots are actual users in Discord, more or less the same as human users. They join your server and then show up in the server's member list. Bots have access to Discord's entire API and can do basically the same things a human can do. Meaning they can send/read/delete/pin messages, create/delete/assign roles, create/delete/edit channels, kick/ban members, all that jazz. They are subject to the same permission system as normal users, so you can use permissions to regulate what a specific bot is allowed to do.

Messages sent by webhooks have more formatting options. You can use named links embeds inside the regular message content instead of just inside embeds, and you can send multiple embeds in one message. With webhooks you can also choose a different username and avatar for each message, while bots, just like humans, have one username and avatar that consistently shows up with every message.

If you want to live-host on a server, most servers (including us and SHA) require a bot instead of a webhook even though all it does is post notifications. Since webhooks are not restricted by permissions, they are a security vulnerability. (the webhook can @everyone with spam or other inappropriate content).

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)



