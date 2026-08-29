**Version 0.70.1 (private beta):**

This is a very early build for v0.70. It is far from feature complete, but we are opening it up for testing regardless.

**Changes from 0.69.19**
- Online resource downloading. A new mechanism to download resources from the internet. (credit jw)
- Tesseract and SV Auto Story require online resources that are not included in the program download.
- FRLG Lucky Egg Farmer has been renamed to Held Item Farmer and extended to support Dragon Fang.
- Lucky Egg and Dragon Fang farmer programs now use the optimal catch method. (credit dolphincurry)
- SwSh+BDSP shiny detection has been optimized and will run better on 4k60.
- Added a new video backend with hardware acceleration.
- Support for Arduino, Teensy, and Pro Micro has been discontinued.

**Notes:**
- The hardware accelerated video backend has only been tested on Windows and is slated for release in v0.71, not v0.70. So it is opt-in and you will need to turn it on manually to use it.
- The download size has not been reduced yet. As of v0.70.1, it is still big. It will reduce before v0.70 goes to public beta.
