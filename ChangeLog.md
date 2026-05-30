**Version 0.65.12:**
- New Program: Pokopia Cloud Reset (credit Gimikyu)
- Large PABotBase2 revamp with a protocol change. You will need to flash new firmware.
- The ESP32-S3 now defaults to "None" instead of "NS1: Wired Controller". We encourage people to use "NS1: Wired Pro Controller" instead since it has more features and can self-diagnose connection issues.
- When flashing the ESP32 and ESP32-S3, you no longer need to manually reset the board by pressing the reset button or power cycling the board. CC will now do this automatically if needed. Therefore, ESP32 and ESP32-S3 can now be remotely flashed without any physical contact.
- Added separate firmware for the non-wireless RP2040 and RP2350 boards. Wiki update coming later.
- All Pico-family boards (including the new generic firmware for RP2040 and RP2350) now support using GPIO 0/1 for UART mode. (selection between GPIO 0/1 vs. GPIO 4/5 is done by placing a jumper on GPIO 26+27.)
- Improved reliability of Y-COMM detector. (reported by Not Dreamer)
- Stability improvements to RNG programs. (reported by Sollisnexus, Sheep Punter, credit Astro)
- Stability improvements to Cram-o-matic. (reported by Thursdays, credit fye)
- Stability improvements to CC application itself.
- 2nd attempt to fix FRLG Game Corner Reset options. (reported by Sheep Punter, credit Astro)

Automated RNG programs are getting close and are slated for v0.66! Please stay tuned!
