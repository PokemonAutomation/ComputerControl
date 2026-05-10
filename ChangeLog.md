
**Version 0.64.7 (private beta):**
- New/Untested Program: Home Living Dex sorter (a variant of the Box Sorter). (credit dolphincurry)
- Includes all changes from 0.64.6 below.

**Version 0.64.6 (public beta):**
- Fixed a major timing issue with PABotBase2. (credit Patrick and others for the clues that revealed this)
- The "HID: Keyboard" controller now displays Num/Caps/Scroll-lock status.
- When using an OEM controller, programs will detect a connection failure and tell you do disconnect other controllers.
- Added an option to make Friend Delete work on the Switch 2. (reported by Nikki)
- Improved stability of AutoStory. (reported by daemon1337, credit jw)
- Fixed high CPU usage with PABotBase2.
- Fixed some glitches for controller status display.

The timing issue in PABotBase2 is very severe as it affects nearly all blind button sequences. Please stay tuned for updates to the RNG programs as they may need to be retuned for new timing parameters.

You will need to flash new PABotBase2 firmware for this release. PABotBase1 is unaffected and remains unchanged.

**Other Announcements:**
 - This is a friendly reminder that AVR8 and PABotBase1 will go away in a few months. So please upgrade to the modern controllers if you haven't already.
 - We are exploring the idea of changing the ESP32-S3's default controller from "NS2: Wired Controller" to "NS1: Wired Pro Controller". This gives default access to gyro, rumble, controller colors, player lights (and thus connection failure detection). But it loses the GL, GR, and C buttons, and requires enabling an extra option in the Switch settings.
