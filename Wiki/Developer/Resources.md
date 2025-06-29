# Resources Folder

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

Some of our automation programs require additional resources in the form of files in a folder named `Resources`. Those files are mostly image files for image matching and JSON files for text-based data. See the [JSON topic](JSON.md) for more details about JSON.

You can download the folder from our latest [program releases](https://github.com/PokemonAutomation/ComputerControl/releases) or from the Github repo [Packages](https://github.com/PokemonAutomation/Packages).
You need to place the `Resources` folder at the same folder hierarchy as the folder of the built **SerialPrograms** executable, so that when launching the executable it can correctly find the resource folder.
For example, if the path of **SerialPrograms** is `C:\git\Arduino-Source\build\SerialPrograms.exe` then the resource folder should be `C:\git\Arduino-Source\Resources`.

If you would like to contribute a new feature to our codebase which relies on a data file, don't forget to upload the data file to our [Packages repo](https://github.com/PokemonAutomation/Packages/tree/master/SerialPrograms/Resources). You can use the same Github development cycle in the [Git guide](Git.md) to submit your new data file.