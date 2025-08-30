# Controller List

This is a full list of devices and controllers that we currently support.

## Setups/Devices

This table lists all the setups that we have along with the controllers that they support.

| | **Device Type** | **Supported Controllers** | **Guides** |
| --- | --- | ------------------------------------------------------------------------ | --- |
| <img src="Images/ControllerSetup-ESP32-S3.jpg" width="200"> | ESP32-S3 | Switch 1: Wired Controller<br>Switch 2: Wired Controller<br>(compatible with Switch 1) | [Guide (Windows)](Controllers/Controller-ESP32-S3.md) |
| <img src="Images/ControllerSetup-ESP32-WROOM.jpg" width="200"> | ESP32-WROOM | Switch 1: Wireless Pro Controller<br>Switch 1: Left Joycon<br>Switch 1: Right Joycon | [Guide (Windows)](Controllers/Controller-ESP32-WROOM.md)<br>[Guide (Mac)](Controllers/Controller-ESP32-WROOM-MacOS.md) |
| <img src="Images/ControllerSetup-Leonardo.jpg" width="200"> | Arduino Uno R3<br>Arduino Leonardo<br>Teensy 2.0<br>Teensy++ 2.0<br>Pro Micro | Switch 2: Wired Controller<br>(compatible with Switch 1) | [Arduino Uno R3](Controllers/Controller-ArduinoUnoR3.md)<br>[Arduino Leonardo](Controllers/Controller-ArduinoLeonardo.md)<br>[Teensy(++) 2.0 (Mini-Grabbers)](Controllers/Controller-Teensy2-MiniGrabbers.md)<br>[Teensy(++) 2.0 (Hammer Headers)](Controllers/Controller-Teensy2-HammerHeaders.md)<br>[Pro Micro (Mini-Grabbers)](Controllers/Controller-ProMicro-MiniGrabber.md)<br>[Pro Micro (Hammer Headers)](Controllers/Controller-ProMicro-HammerHeaders.md) |
| <img src="Images/ControllerSetup-sbb.jpg" width="200"> | sys-botbase 2/3 | Switch 1: Wired Pro Controller | [sys-botbase](Controllers/Controller-sys-botbase.md) |

## Controller Types

**Switch 1: Wired Controller**

This is the standard 3rd party wired that most "officially licensed" controllers use. They only support the standard buttons/joystick and do not support rumble or gyro. They also do not support custom colors in their icon when connected to the Switch.

These use the standard 8-byte HID report type with 14 buttons, a dpad, and two joysticks with 8-bit precision.

**Switch 2: Wired Controller**

This is the same as the Switch 1 wired controller, except that they add the GL, GR, and C (gamechat) buttons for the Switch 2. This controller type is backwards compatible with the Switch 1 such that pressing the new buttons simply do nothing on the Switch 1.

These also use the standard 8-byte HID report type with 17 buttons, a dpad, and two joysticks with 8-bit precision. Due to the button field having only 16 bits, the 17'th button (the C button) instead uses an unused bit in the dpad byte.

**Switch 1: Wireless Pro Controller**

This is the official pro controller from Nintendo - connected wirelessly to the Switch.

At this time, this project does not support gyro, rumble, NFC, or console wake up. So in effect, it is functionally the same as the wired controller - though less stable due to wireless communication.

This uses Nintendo's proprietary 48-byte HID report 0x30.

**Switch 1: Left + Right Joycons**

These are the official joycons from Nintendo - connected wirelessly to the Switch.

At this time, this project does not support gyro, rumble, NFC, or console wake up.

This uses Nintendo's proprietary 48-byte HID report 0x30.

**Switch 1: Wired Pro Controller**

This is the official pro controller from Nintendo - connected to the Switch over USB.

Currently, the only implementation we have is sys-botbase. It does not use reports and instead, directly sets the controller state by writing to system memory.


## Controller Performance Classes

For the purposes of program compatibility, each setup/device + controller combination is placed into one of 3 performance categories:

- Wired
- Wireless
- sys-botbase 2

Programs that are speed-critical will have separate execution paths optimized for each performance category. (i.e. date spam, Fast Code Entry...)

**Wired:**

Wired controllers are by far the most stable with a button timing accuracy of < 1ms (typically ~100us). This makes it the best suited for automation.

| **Device** | **Controller** |
| --- | --- |
| ESP32-S3 | Switch 1: Wired Controller<br>Switch 2: Wired Controller |
| Arduino Uno R3<br>Arduino Leonardo<br>Teensy 2.0<br>Teensy++ 2.0<br>Pro Micro | Switch 2: Wired Controller |
| sys-botbase 3 (sbb3) | Switch 1: Wired Pro Controller |


**Wireless:**

Wireless controllers are less table and usually have timing variation on the order of 2-10ms. Wireless controllers are generally less reliable since they are prone to random disconnects and high latencies from wireless interference. Nintendo's complicated (and proprietary) wireless protocol means that 3rd party implementations (including this project) are typically less than perfect and prone to compatibility issues.

| **Device** | **Controller** |
| --- | --- |
| ESP32 | Switch 1: Wireless Pro Controller<br>Switch 1: Left Joycon<br>Switch 1: Right Joycon |


**sys-botbase 2:**

This category exists simply because sys-botbase 2 (sbb2) is extremely unstable with timing variations upwards of 150ms along with massive throughput issues due to backpressure. As a result, many programs written for the above wired and wireless controllers do not work on sbb2.

With the launch of sys-botbase 3 (sbb3), this setup has been deprecated.

| **Device** | **Controller** |
| --- | --- |
| sys-botbase 2 (sbb2) | Switch 1: Wired Pro Controller |


<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)






