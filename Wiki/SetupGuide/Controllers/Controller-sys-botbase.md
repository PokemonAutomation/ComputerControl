# Controller Setup: sys-botbase

This sys-botbase setup is intended for experienced CFW (custom firmware) Switch users who want to try out our computer-control (CC) programs without buying all the additional hardware that is needed.

If you do not have CFW (and are thus starting from scratch), we [recommend going back](../README.md#the-controller-the-computers-hands) and choosing one of the other controller options as they are more reliable than this option. You do not need CFW or sys-botbase to run CC programs. Likewise, the CC programs only use sys-botbase for its controller. It does not touch any of its "hacking" features like reading and modifying game memory.

Since this is intended for existing CFW users, we will not cover how to hack your Switch or to setup CFW.

Our current sys-botbase support only covers the wired pro controller. So it will not be able to run any LGPE programs.

## Hardware Setup:

**Required Hardware (Full List):**
1. A regular [Nintendo Switch](../README.md#video-capture-card-the-computers-eyes) and its accessories (dock, power cable, HDMI cable). (You cannot use a Switch Lite.)
2. A [computer](../README.md#the-computer-the-player) running x64 Windows. (or another OS if you are able to set it up.)
3. A [video capture card](../README.md#video-capture-card-the-computers-eyes).

**Estimated Total Cost (USD):** (not including computer and Nintendo Switch)
- **Single Setup:** $10 - $20 (for the capture card)
- **Bulk Purchase:** (no discounts over single setup)

All of these are part of the initial setup. If your Switch is already running CFW, then no further hardware is needed. If not, then this guide is not for you.

Since there is no additional hardware, there are no additional hardware setup instructions!

## Software Setup:

### Step 0: Getting Ready

Make sure you have everything else setup so that it looks like this:

<img src="../Images/GeneralSetup-CC.png">

If not, you should go back to the [general setup guide](../README.md) and start over.

### Step 1: Install sys-botbase and ldn-mitm

If you are reading this, you probably already have these setup. If not, [here's the guide](https://github.com/kwsch/SysBot.NET/wiki/Bot-Startup-Details).

### Step 2: Navigate your Switch to where it will accept a new controller.

sys-botbase will create a virtual wired controller that behaves like a real controller. So it can only connect if your Switch is ready for it.

Places where the Switch will accept a new controller:
1. The grip menu.
2. The Switch home or settings.
3. In a game when no other controllers are connected.

<img src="../Images/GripMenu.png">

### Step 3: Connect to the Switch

1. At the top for the "Controller" option, click the dropdown and select `TCP: sys-botbase` .
2. Enter the IP address and port of your Switch. (e.g. `192.168.1.123:6000`)

If everything worked correctly, it will look like this:

<img src="../Images/ControllerSetup-sbb-Connected-Labled.png">

If not, see [troubleshooting](#troubleshooting).

### Step 4: Test the connection

You can control your Switch from the keyboard. Click on the video display to activate the keyboard controls. Then try pressing some buttons. You can view the keyboard -> controller mapping by clicking on the "keyboard layout" at the bottom left corner of the program.

We recommend familiarizing yourself with the keyboard controls as this is the preferred way to control your Switch while setting up to run a program. In effect you can play your Switch from your computer. While it's not as nice as using a native controller, it is good enough to easily setup programs - especially if you're doing this remotely where you do not have physical access to the Switch.

The default layout is the standard WASD setup for FPS games on the most common QWERTY keyboard layout. If you don't like it or you have a different keyboard layout, you can change the key mappings in the "Framework Settings" panel at the top of the program list to the left.

<img src="../Images/ControllerSetup-sbb-Controls.png">

### Step 5: You are done!

If keyboard commands are working (along with video and audio), you are done!

Try clicking on other programs on the sidebar. You will find that all of them are "virtual consoles" that will accept keyboard commands. At the top of every program is a link to the wiki that explains how to setup and use that program.

Continue on to [Finishing Up](../README.md#step-4-finishing-up)!


## Troubleshooting:

### Stuck on "Not Connected"

<img src="../Images/ControllerSetup-sbb-NotConnected.png">

This usually means the IP address is wrong.

### Stuck on "Connecting" or "Timed Out"

<img src="../Images/ControllerSetup-sbb-Connecting.png">

Try clicking "Reset Ctrl". This can sometimes fix intermittent issues.

These are standard network connection issues. Common causes:
 - The IP address is wrong or there is no network path from your computer to the Switch.
 - A firewall (either on your computer or your network) is blocking the connection.
 - sys-botbase is not installed correctly.
 - sys-botbase is already running a controller and is not accepting another one.
 - Local connection is enabled and ldn-mitm is not enabled. This will block the network connection.
 - You have dual-band wifi where your Switch is connected to one band while your computer is connected to the other.

Sometimes, an older connection does not shutdown properly causing new connections to fail (i.e. a zombie state). You can try undocking your Switch and going in/out of a game several times, similarly with airplane mode. Otherwise, you may need to reboot the Switch.


### Connected, but keyboard commands don't work.

This usually means that you have another controller connected to the Switch and it has priority over sbb. Try disconnecting that controller.

Most programs will block keyboard inputs if the program is running. So if you happen to be running a program and it ignores your keyboard commands, this is expected.

### Response time is very high

<img src="../Images/ControllerSetup-sbb-HighLatency.png">

The response time is how long it takes to round-trip from your computer to sys-botbase and back. It will always be longer than a ping due to overhead within sys-botbase and/or Atmosphere.

It should be less than 5ms, but can occasionally spike to over 100ms during periods of high traffic. This is normal. But if it stays above 50ms, you will have difficulty running many of the programs. So you will want to fix this. (usually by improving your network connection)

Sometimes the Switch will get into a temporary slow state where this response time stays very high (> 100ms). This can usually be cleared by rebooting the Switch.

Overall, this is not great and is why sys-botbase is less reliable than the other (microcontroller) options which are usually <1ms latency.

### "Last Ack: xxx seconds ago"

<img src="../Images/ControllerSetup-sbb-LastAck.png">

This means the Switch has stopped responding to the computer's commands. The most common (unobvious) cause of this is that the Switch entered local connection mode because you didn't have ldn-mitm enabled. Because sys-botbase relies on the network connection to communicate with the Switch, going into local connection mode will kill this connection. So while sys-botbase is still running on the Switch, no commands are getting through.


### "Cannot start program. The controller is missing the feature: TickPrecise"

<img src="../Images/ControllerSetup-sbb-TickPrecise.png">

sys-botbase lacks the timing precision that the Arduino can achieve. Therefore programs that require precise controller timings will not run reliably over sys-botbase and are therefore blocked from running. (we don't want people to file bugs when they run the program and it breaks)

The programs on the sidebar are color-coded on what controllers they can run on:
- **Blue:** Runs on all controllers with no issues.
- **Green:** Runs on all controllers, but will have degraded performance/reliability on imprecise controllers (such as sys-botbase).
- **Purple:** Only runs on precise controllers. (will not run on sys-botbase)
- **Red:** Specialized programs that only run on specific controllers. (will not run on sys-botbase)

Thus sys-botbase can only run blue and green programs. For everything else, you will need to use one of the [microcontroller setups](README.md#the-controller-the-computers-hands).

If you are a sysmodule developer and are interested in fixing sys-botbase, please hit us up in [Discord](https://discord.com/channels/695809740428673034/709201831066206268) to discuss. We think we know what the problem is and we have ideas on how to fix it. But we have neither the expertise nor the developer bandwidth to do it ourselves.


### Multi-Switch programs don't work.

Multi-Switch programs generally involve the two Switches using local communication to talk to each other. ldn-mitm will block local connections which means the two Switches cannot connect unless both are running ldn-mitm. Turning off ldn-mitm to allow the local communication mode will kill the network connection to the computer.

There is no general solution to this. For some programs, you may be able to work-around this by having both Switches go online. But this is not possible for programs that require resetting the game.

Using ethernet instead of wireless does not solve this problem as local communication mode will kill this as well.


### usb-botbase

usb-botbase is (generally) not an option because it requires the same USB port that is needed for the HDMI output.















<hr>

**Credits:**
- Kuroneko/Mysticial

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)





