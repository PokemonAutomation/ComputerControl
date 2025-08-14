# Flash the ESP32(-S3) using esptool

This is an alternate method to flash the ESP32(-S3).

## Install esptool
See the official instructions here: https://docs.espressif.com/projects/esptool/en/latest/esp32/installation.html

Briefly:
- install [Python](https://www.python.org/downloads/)
- Open the terminal
    - to confirm your Python installation: type into terminal: `python --version`
- Type in terminal: `pip install esptool`
- if you receive an error, try:
    - `python -m pip install esptool`
    - or `pip3 install esptool`
- Type in terminal: `pip install setuptools`

## Flash the ESP32(-S3) using esptool
- Open the terminal
- Change the directory to the directory containing the .bin file
    - e.g. Type in terminal: cd `[path to directory]`
- Type in terminal: `esptool -p [PORT] write-flash 0x0 [ESP32-(S3).bin]`
    - Replace `[PORT]` with your ESP32-S3 board's USB port name. e.g. COM5. You can find this using the Device Manager.
    - Replace `[ESP32-(S3).bin]` with the ESP32 or ESP32-S3 .bin file that you want to flash.
    - Sometimes the flash can fail without reason. If it fails, try running the flash command again.

# Flash the ESP32(-S3) using Espressif's ESP-IDF

## Install ESP IDF with VS Code

See the guide here: https://github.com/espressif/vscode-esp-idf-extension/?tab=readme-ov-file#install

Briefly:
- Download and Install VSCode
- Install ESP-IDF system prerequisites for your operating system:
    - Prerequisites for [MacOS and Linux](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/linux-macos-setup.html).
    - For Windows there are no additional prerequisites.
- Install the ESP-IDF extension in VSCode
- Press `F1`. Then, type in and select `Configure ESP-IDF extension`.
- Select `Express` mode
- Under the `Select ESP-IDF version:` dropdown, select the latest release version.
- Choose directories for the `ESP-IDF directory (IDF_PATH)` and the `ESP-IDF Tools directory (IDF_TOOLS_PATH)`. 
    - These two directories should be different.
- Click `Install`

## Flash the ESP32(-S3) using ESP-IDF terminal in VS Code
- Install ESP-IDF in VS Code as above
- Press `F1`. Then, type in and select `Open ESP-IDF terminal`.
- In terminal, change directory of the ".bin" file.
    - `cd [path to directory]`
- Run in ESP-IDF terminal: `esptool -p [PORT] write_flash 0x0 [ESP32-(S3).bin]`
    - Replace `[PORT]` with your ESP32-S3 board's USB port name. e.g. COM5. You can find this using the Device Manager.
    - Replace `[ESP32-(S3).bin]` with the ESP32 or ESP32-S3 .bin file that you want to flash.
    - NOTE: as of this writing, ESP-IDF does not come bundled with the latest esptool, so it only supports `write_flash`, and not `write-flash`.
    - Sometimes the flash can fail without reason. If it fails, try running the flash command again.


# For Developers only

## Install a different version of ESP-IDF
- Install ESP-IDF in VS Code as above
- Press `F1`. Then, type in and select `Configure ESP-IDF extension`.
- Select `Express` mode
- Under the `Select ESP-IDF version:` dropdown, select your desired version. You can also point this to a directory with a custom version of ESP-IDF.
- Choose directories for the `ESP-IDF directory (IDF_PATH)` and the `ESP-IDF Tools directory (IDF_TOOLS_PATH)`. 
    - These two directories should be different.
    - `IDF_PATH`: this contains the version-specific ESP-IDF
    - `IDF_TOOLS_PATH`: this contains tools that are used across different ESP-IDF versions. 
    - e.g. My folder setup:
        - `IDF_PATH`: D:\esp\v5.5, D:\esp\v5.4, D:\esp\esp-custom
        - `IDF_TOOLS_PATH`: D:\esp\tools (same across different versions/installations)
- Click `Install`

## Change ESP-IDF version
- Make sure you have installed your desired ESP-IDF as above (see Install a different version of ESP-IDF).
- Press `F1`. Then, type in and select `Configure ESP-IDF extension`.
- Select `Use Existing Setup`
- Select the ESP-IDF version that you want to use.

<hr>

**Credits:**
- jw

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)




