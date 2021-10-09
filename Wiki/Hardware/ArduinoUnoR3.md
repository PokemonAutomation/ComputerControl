# Hardware - Arduino Uno R3

This section covers the required hardware for users who have the Arduino Uno R3.

## Hardware Requirements

**Microcontroller Hardware:**

Make sure you have all the [microcontroller hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/ArduinoUnoR3.md).

**Buy the following additional components:**

1. Serial Board (**Pick one**)
    1. UART Cable ([CP210x controller](https://www.adafruit.com/product/954))
      > ***Avoid the Prolific (PLxxxx) controllers. Many of them are knock-offs that do not work.***
      >  The Adafruit UART cable is reliable and beginner-friendly, but it is also quite expensive.
   2. CP210x board ([4 for $8](https://www.amazon.com/gp/product/B07T1XR9FT)) | ([2 for $8](https://www.amazon.com/gp/product/B07D6LLX19/)) | ([1 for $8](https://www.amazon.com/dp/B072K3Z3TL))
      >  If you are experienced (or confident), these are some cheaper alternatives which also work. These may require a trivial amount of extra wiring.
2. Jumper Wires ([example](https://www.amazon.com/gp/product/B01EV47GI4/))
3. Video capture card ([example](https://www.amazon.com/gp/product/B088HBRM7T))
4. HDMI cable(s)

## Hardware Assembly

Once you have your hardware, you need to make some connections.

Make the following connections:
- UART cable green (TX) to Arduino pin1 (TX -> 1)
- UART cable white (RX) to Arduino pin0 (RX <- 0)
- UART cable black (GND) to Arduino GND (any one is fine)
- UART cable red (VCC) – leave unconnected

<img src="images/uart-uno-0.jpg" height="600"> <img src="images/uart-uno-1.jpg" height="600">




## Next Steps

Continue to the [software tutorial](/Wiki/Software/README.md).


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)





