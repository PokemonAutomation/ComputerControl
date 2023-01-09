# Hardware - Teensy 2.0 and Teensy++ 2.0

This section covers the required hardware for users who have Teensy 2.0 or Teensy++ 2.0.

## Hardware Requirements

Make sure you have all the [microcontroller and serial hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/Teensy2.md) and [video hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/Hardware.md#video-hardware).

## Hardware Assembly

There are many ways to set this up with varying cost and difficulty. Here we will present some simple options that do not require soldering. If you are experienced with electronics, feel free to do your own thing.

It is worth noting that the most difficult part of the serial setup is connecting to the holes on the Teensy.
This can be made much easier by purchasing a Teensy with pins, but this is not recommended unless you plan on keeping the Teensy in a breadboard as it is too easy to damage or short the pins.

Here are the two options covered in this tutorial:
- [**Option 1:** UART Cable + Mini-Grabber Cables](#option-1-uart-cable--mini-grabber-cables)
- [**Option 2:** UART Cable + Solderless Hammer Headers](#option-2-uart-cable--solderless-hammer-headers)

<hr>

### Option 1: UART Cable + Mini-Grabber Cables

This option is the easiest to setup, however the mini grabber cables that are needed are rarely in stock.

<img src="images/serial-teensy2-mg.jpg" height="300"> <img src="images/serial-teensypp2-mg.jpg" height="300">

**Required Hardware:**
1. The [microcontroller hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/Teensy2.md).
2. A [USB-to-TTL UART cable or board](https://www.adafruit.com/product/954). It is recommended to get one with the CP210x controller.
> ***Avoid the Prolific (PLxxxx) controllers. Many of them are knock-offs that do not work.***
3. [Mini grabber to jumper wires (male).](https://www.amazon.com/gp/product/B08M5GNY47) You want the one with ***male*** jumper wires.

<img src="images/uart-adafruit.jpg" height="200"> <img src="images/mini-grabber.jpg" height="200">

**Hardware Setup:**

Once you have your hardware, you need to make some connections. These are the same for both Teensy 2.0 and Teensy++ 2.0, but the locations of the holes are different. Refer to the images.

Make the following connections:
- UART cable green (TX) to Teensy D2 (RX)
- UART cable white (RX) to Teensy D3 (TX)
- UART cable black (GND) to Teensy GND (any one is fine)
- UART cable red (VCC) – leave unconnected

Note that the mini grabber clips may not fit through the holes on the Teensy. This is fine.

**Teensy 2.0:** (click on images to enlarge)

<img src="images/serial-teensy2-mg-0.jpg" height="200"> <img src="images/teensy2-mg-1.jpg" height="200">

**Teensy++ 2.0:** (click on images to enlarge)

<img src="images/serial-teensypp2-mg-0.jpg" height="200"> <img src="images/teensypp2-mg-1.jpg" height="200">

<hr>

### Option 2: UART Cable + Solderless Hammer Headers

This option is cleaner, but is more involved.

<img src="images/teensy2-hammer-0.jpg" height="300"> <img src="images/teensypp2-hammer-0.jpg" height="300">

**Required Hardware:**
1. The [microcontroller hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/Teensy2.md).
2. A [USB-to-TTL UART cable or board](https://www.adafruit.com/product/954). It is recommended to get one with the CP210x controller.
> ***Avoid the Prolific (PLxxxx) controllers. Many of them are knock-offs that do not work.***
3. [Solderless Hammer Headers](https://www.adafruit.com/product/3662)
4. A box cutter or a wire cutter.
5. Pliers. (you will likely need two of them)

<img src="images/uart-adafruit.jpg" height="200"> <img src="images/hammer-headers.jpg" height="200">

**Hardware Setup:**

1. Use your box cutter or wire cutter to cut out 2 pairs of pins from the strip of solderless headers. ***Be very careful not to cut yourself.***
2. Insert a pair of hammer headers into the D2 and D3 holes on the Teensy.
3. Insert a hammer header into the GND hole on the Teensy. (Since you can't easily split the pair of pins, you can do GND and the pin adjacent to it.)

<img src="images/teensy-hammers-0.jpg" height="200"> <img src="images/teensy-hammers-1.jpg" height="200">

On Teensy 2.0, you need a LOT of force to push the hammer headers into the holes. Recommend using pliers to pull the pins out of the plastic holds and inserting the long side into the Teensy. Then put the covers back on and use pliers to squeeze it in.

Now that the pins are setup, you can make the connections. These are the same for both Teensy 2.0 and Teensy++ 2.0, but the locations of the holes are different. Refer to the images.

You will need to make the following connections:
- UART cable green (TX) to Teensy D2 (RX)
- UART cable white (RX) to Teensy D3 (TX)
- UART cable black (GND) to Teensy GND (any one is fine)
- UART cable red (VCC) – leave unconnected

<img src="images/teensy2-hammer-1.jpg" height="200"> <img src="images/teensypp2-hammer-1.jpg" height="200">




## Next Steps

Continue to the [software tutorial](/Wiki/Software/README.md).


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)





