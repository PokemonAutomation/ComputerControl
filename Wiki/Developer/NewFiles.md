# Add New Files

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

If you add or remove code files in the source-code folder, you need to update the file list in [CMakeLists.txt](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/CMakeLists.txt) and [SerialPrograms.pro](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/SerialPrograms.pro).

If you know a bit about Python, we have a Python script [add_new_file.py](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Scripts/add_new_file.py) to help you to add a new file to those file lists. For example:
```
python3 Arduino-Source/SerialPrograms/Scripts/add_new_file.py Source/<some_middle_path>/Pokemon_NewFile.h
```
This adds the path of Pokemon_NewFile.h to both CMakeLists.txt and SerialPrograms.pro.

## Panels

If you are adding a new program and want the program to show up in the side panel in the UI, you also need to add your program to \<GameName\>_Panels.cpp. e.g. For a Pokemon Scarlet/Violet game, add the program to PokemonSV_Panels.cpp.