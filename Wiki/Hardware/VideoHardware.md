# Video Hardware:

The video capture hardware is separate from the device controller emulation. Therefore it's the same for all microcontroller devices.

**Required Hardware:**

1. A video capture card. (**Choose one based on your needs**) 
   1. Capture Card w/o TV output (Budget buy) ([example](https://www.amazon.com/dp/B097R3PB36))
   > The cheapest ones can be less than $10. However, they have no TV output, are limited to USB 2.0 bandwidth, and may have video quality issues.
   2. Loop-Out Card (Good middle ground, but expensive) 
   > if you want a tolerable video quality you'll want one that uses USB 3.0.
   3. Pass-Through Card (If you want to live-stream) ([example](https://www.amazon.com/product/dp/B08L64XT3J/))
   > If you want to display the video both on your TV and in your computer, you will need one with TV output with pass-through.
   > The more expensive ones can be over $100. These support TV output and use USB 3.0 or PCIe. These are meant for livestreaming.
2. HDMI cable(s)
   > Regardless of what capture card(s) you choose, you will need either 1 or 2 HDMI cables to connect them to your Switch and/or your TV.

Note: For the purposes of Pokémon automation, the cheapest capture cards ([example](https://www.amazon.com/gp/product/B088HBRM7T)) appear to be sufficient. But if you want a tolerable video quality you'll want one that uses USB 3.0. And if you want to display the video both on your TV and in your computer, you will need one with TV output with pass-through. Each of these will add to the cost.

Note: **DO NOT** purchase AverMedia capture cards! Those cards use an old API that is no longer supported by our program after v0.14.

# Capture Card Type Explanations

### Capture card without TV output:

Display video only with your computer. (Price Range: $10 - $20; depending on USB 2.0 or 3.0)

<img src="https://raw.githubusercontent.com/PokemonAutomation/SwSh-Arduino/master/Documentation/Tutorials/images/capture-card-nopt.jpg" height="400">

### Capture card with TV output:

Display video both on TV and in your computer.

<img src="https://raw.githubusercontent.com/PokemonAutomation/SwSh-Arduino/master/Documentation/Tutorials/images/capture-card-pt.jpg" height="400">

**Pass-Through vs. Loop-Out:**

Capture cards with both computer and TV output come in two flavors:
- Pass-Through (Price Range: > $40)
- Loop-Out (Price Range: > $25)

Pass-Through cards are generally more expensive, but they have the lowest latency from the console to the computer (even lower than the capture cards without TV output).

If you intend to do any serious gameplay from your computer, it is highly recommended to get a pass-through card even if you don't intend to display to a TV. Loop-out cards and cards without TV output have a high enough latency that it may be difficult to play on the computer.


## Software Setup

This step is optional since it isn't needed for Pokémon automation, but recommended anyway for everyone who has a video capture device.

Once you have your video hardware, download and install [OBS](https://obsproject.com/download). Learn how to use OBS, as it's the standard for streaming recording and will be useful for troubleshooting your hardware setup. If you can get OBS to access your Switch video stream, then your capture card is properly recognized by your computer and is ready to use.

Aside from streaming their gameplay, many users use OBS to record their shiny hunts to determine if a shiny is star or square before deciding whether to catch it or pass it up.

This guide will not go into detail on how to use OBS. There should be plenty of other online resources for that.

Note: our program used to be able to load video stream from a virtual camera created by OBS, so the video stream went: Switch -> OBS virtual camera -> our program.
But as of now (2022) our program no longer supports virtual camera.
If you would like to use OBS to stream Pokémon automation, you need to let OBS stream the video window of our program.
Double clicking on the stream view of our program will pop up the stream view as an independent window. You can then use OBS to capture this window.

<img src="https://raw.githubusercontent.com/PokemonAutomation/SwSh-Arduino/master/Documentation/Tutorials/images/obs.png" height="600">

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

