# Hardware - Pro Micro

This section covers the required hardware for users who have the Pro Micro.

## Hardware Requirements

**Microcontroller Hardware:**

Make sure you have all the [microcontroller hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/ProMicro.md).

**Buy the following additional components:**
1. Serial Board (**Pick one**)
   1. UART Cable ([CP210x controller](https://www.adafruit.com/product/954))
      >  ***Avoid the Prolific (PLxxxx) controllers. Many of them are knock-offs that do not work.***
      >  The Adafruit UART cable is reliable and beginner-friendly, but it is also quite expensive.
   2. CP210x board ([4 for $8](https://www.amazon.com/gp/product/B07T1XR9FT)) | ([2 for $8](https://www.amazon.com/gp/product/B07D6LLX19/)) | ([1 for $8](https://www.amazon.com/dp/B072K3Z3TL))
      >  If you are experienced (or confident), these are some cheaper alternatives which also work. These may require a trivial amount of extra wiring.
2. Board Connection (**Pick one**)
   1. Mini-Grabber to Male jumper wires ([example](https://www.amazon.com/gp/product/B08M5GNY47))
       > Easiest option, but item is hard to find
   2. Solderless Hammer Headers ([example](https://www.adafruit.com/product/3662))
       > Fairly easy to install. Ensure you are getting _hammer headers_, they will have a bulge on the short side to hold the pins in place
   3. Hammer Headers ([example](https://www.adafruit.com/product/2822))
       > Most difficult option! You will **need** to solder with this option. Please only pick it if you are comfortable soldering.
3. Video capture card ([example](https://www.amazon.com/gp/product/B088HBRM7T))
4. HDMI cable(s)

## Hardware Assembly

There are many ways to set this up with varying cost and difficulty. Here we will present some simple options that do not require soldering. If you are experienced with electronics, feel free to do your own thing.

Here are the two options covered in this tutorial:
- [**Option 1:** UART Cable + Mini-Grabber Cables](#option-1-uart-cable--mini-grabber-cables)
- [**Option 2:** UART Cable + Solderless Hammer Headers](#option-2-uart-cable--solderless-hammer-headers)

<hr>

### Option 1: UART Cable + Mini-Grabber Cables

This option is the easiest to setup, however the mini grabber cables that are needed are rarely in stock.

<img src="images/serial-pro-micro-mg.jpg" height="400">

**Required Hardware:**
1. The [microcontroller hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/ProMicro.md).
2. A [USB-to-TTL UART cable or board](https://www.adafruit.com/product/954). It is recommended to get one with the CP210x controller.
> ***Avoid the Prolific (PLxxxx) controllers. Many of them are knock-offs that do not work.***
3. [Mini grabber to jumper wires (male).](https://www.amazon.com/gp/product/B08M5GNY47) You want the one with ***male*** jumper wires.

<img src="images/uart-adafruit.jpg" height="200"> <img src="images/mini-grabber.jpg" height="200">

**Hardware Setup:**

Once you have your hardware, you need to make some connections.

Make the following connections:
- UART cable green (TX) to Pro Micro RX1
- UART cable white (RX) to Pro Micro TX0
- UART cable black (GND) to Pro Micro GND (any one is fine)
- UART cable red (VCC) – leave unconnected

Note that the mini grabber clips may not fit through the holes on the Pro Micro. This is fine.

<img src="images/serial-pro-micro-mg-0.jpg" height="200"> <img src="images/serial-pro-micro-mg-1.jpg" height="200">

<hr>

### Option 2: UART Cable + Solderless Hammer Headers

This option is cleaner, but is more involved.

<img src="images/pro-micro-hammer-0.jpg" height="400">

**Required Hardware:**
1. The [microcontroller hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/ProMicro.md).
2. A [USB-to-TTL UART cable or board](https://www.adafruit.com/product/954). It is recommended to get one with the CP210x controller.
> ***Avoid the Prolific (PLxxxx) controllers. Many of them are knock-offs that do not work.***
3. [Solderless Hammer Headers](https://www.adafruit.com/product/3662)
4. A box cutter or a wire cutter.
5. Pliers. (you will likely need two of them)

<img src="images/uart-adafruit.jpg" height="200"> <img src=images/hammer-headers.jpg" height="200">

**Hardware Setup:**

1. Use your box cutter or wire cutter to cut out 2 pairs of pins from the strip of solderless headers. ***Be very careful not to cut yourself.***
2. Insert a pair of hammer headers into the TX and RX holes on the Pro Micro.
3. Insert a hammer header into the GND hole on the Pro Micro. (Since you can't easily split the pair of pins, you can do GND and the pin adjacent to it.)

<img src="images/pro-micro-hammers-0.jpg" height="200"> <img src="images/pro-micro-hammers-1.jpg" height="200">

You will need a LOT of force to push the hammer headers into the holes. Recommend using pliers to pull the pins out of the plastic holds and inserting the long side into the Pro Micro. Then put the covers back on and use pliers to squeeze it in.

Now that the pins are setup, you can make the connections.
- UART cable green (TX) to Pro Micro RX1
- UART cable white (RX) to Pro Micro TX0
- UART cable black (GND) to Pro Micro GND (any one is fine)
- UART cable red (VCC) – leave unconnected

<img src="images/pro-micro-hammer-1.jpg" height="400">




## Next Steps

Continue to the [software tutorial](/Wiki/Software/README.md).


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)








