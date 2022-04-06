# Hardware - Arduino Leonardo

This section covers the required hardware for users who have the Arduino Leonardo.

<img src="images/leonardo.jpg" height="600"> 

## Hardware Requirements

**Microcontroller Hardware:**

Make sure you have all the [microcontroller hardware](https://github.com/PokemonAutomation/Microcontroller/blob/master/Wiki/Hardware/ArduinoLeonardo.md).

**Buy the following additional components:**

1. Serial Board (**Pick one**)
   1. UART Cable ([CP210x controller](https://www.adafruit.com/product/954)) Adafruit UART cable is not the cheapest, but it is the most beginner-friendly.<br><br>
      ***DO NOT get the Prolific (PLxxxx) controllers.* They do not work and they are explicitly blocked in the program.**<br><br>They are cheap because they do not work. If you buy it anyway, you will be wasting your time and money.<br><br>**YOU HAVE BEEN WARNED!**<br><br>
   2. CP210x board ([4 for $8](https://www.amazon.com/gp/product/B07T1XR9FT)) | ([2 for $8](https://www.amazon.com/gp/product/B07D6LLX19/)) | ([1 for $8](https://www.amazon.com/dp/B072K3Z3TL))
      >  If you are experienced (or confident), these are some cheaper alternatives which also work. These may require a trivial amount of extra wiring.
2. Jumper Wires ([example](https://www.amazon.com/gp/product/B01EV47GI4/))
3. Video capture card ([example](https://www.amazon.com/gp/product/B088HBRM7T))
4. HDMI cable(s)

## Hardware Assembly

Once you have your hardware, you need to make some connections.

Make the following connections:
| **UART pin** | **Adafruit UART Wire Color** | **Arduino Leonardo pin** |
| --- | --- | --- |
| TX | Green | TX -> 1 (pin1) |
| RX | White | RX <- 0 (pin0) |
| GND | Black | GND (any one is fine) |
| VCC | Red | Leave unconnected |

<img src="images/leonardo-1.jpg" height="600">
(Image from alexk#8946)



## Next Steps

Continue to the [software tutorial](/Wiki/Software/README.md).


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)






