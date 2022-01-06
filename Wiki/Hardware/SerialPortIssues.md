# Serial Port issues

Having issues getting your serial device to connect to the Switch? If it isn't a wiring issue or needing to re-flash the hex to the device; you may need to uninstall the CP210x drivers and reinstall.

_INSERT IMAGE OF WHAT ERROR LOOKS LIKE_

1. Open "Device Manager"
2. Navigate to "Ports (COM & LPT)
3. Right click on your serial device (ex: Silicon Labs CP210x USB to UART Bridge)

_INSERT IMAGE OF DEVICE MANAGER SHOWING PORTS_

4. Click Properties
5. Click uninstall device
6. Go through with uninstalling it completely

_INSERT IMAGE OF COM3 PROPERTIES_

7. Download and install these [drivers](https://www.silabs.com/documents/public/software/CP210x_Windows_Drivers.zip)
