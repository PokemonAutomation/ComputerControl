# Computer-Control Programs - Hardware Guide

This is the guide for buying and setting up the hardware for the computer-control programs.

If you already have the hardware, skip ahead to the software tutorial.
- [Software Tutorial](/Wiki/Software/README.md)


## Before you Begin

Before you begin, make sure you meet all of the following requirements:

1. You have a working [microcontroller setup](https://github.com/PokemonAutomation/Microcontroller) and you know how to run microcontroller programs. **(DO NOT SKIP the Microcontroller tutorial. It provides the necessary background to run Computer-Control.)**
2. You have computer running 64-bit Windows (Windows 10 or newer) or macOS. As of this writing, no other platforms are supported. But if you use Linux, then you may be knowledgeable to adapt our macOS guide to work for your Linux. 
3. You have a regular Switch (not a Switch Lite) if you want to use programs requiring video feedback.
4. Be willing to spend an additional $20 - $50 USD for the new hardware.

Your computer must be sufficiently powerful:

- If you intend to control **1** Switch: A dual-core processor @ 3 GHz no older than 2015 should be sufficient.
- If you intend to control **2** Switches: A quad-core processor @ 3 GHz no older than 2015 should be sufficient.
- If you intend to control **4** Switches: 6-8 cores minimum.

**Important (since this happens a lot):**

If you...

- Do not already have a suitable computer.
- Are on a budget.
- Are considering getting a cheap computer just to run this project. (under $1000 USD)

***Stop right there. Don't do it.***

Video recognition and machine learning require a lot of computing power which cheap computers simply cannot handle. And computational requirements will increase as the Pokémon games become increasingly difficult to automate and require increasingly advanced recognition methods.

We started Pokémon Automation as a fun thing for gamers who already had a decent computer. We never expected (nor do we encourage) people to break the bank for it.


## Serial Hardware

In order to use computer-control programs, your computer needs to be able to control your game console (duh!).

The way we do it is by using a [serial connection](https://en.wikipedia.org/wiki/Serial_port) to connect the microcontroller to the computer. This allows the computer to take control of your game console.

<img src="images/serial-setup.jpg">


The serial hardware setup will depend on what microcontroller you have.

- [Arduino Leonardo](ArduinoLeonardo.md)
- [Teensy 2.0 and Teensy++ 2.0](Teensy2.md)
- [Pro Micro](ProMicro.md)
- [Arduino Uno R3](ArduinoUnoR3.md)

## Video Hardware

Some programs also need to see the screen! So a video capture card is also needed. See the capture card guide [here](VideoHardware.md).

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

