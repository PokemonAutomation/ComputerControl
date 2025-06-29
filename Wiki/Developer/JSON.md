# Use JSON

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

Hardcoding all Pokémon names in a C++ source file is not fun. A better software development practice is to store those lengthy data as external files. At runtime, the executable loads the file to use the data.
We use [JSON](https://en.wikipedia.org/wiki/JSON) as the file format to store our text-based data like Pokémon lists and Pokédex contents.
An example is [Pokedex-National.json](https://github.com/PokemonAutomation/Packages/blob/master/SerialPrograms/Resources/Pokemon/Pokedex/Pokedex-National.json), in our `Resources` folder. See [its topic](Resources.md) for more details about the folder.

## JSON for Sprites

For better user experience we also have Pokémon sprite images in `Resources` folder. Those sprites are used as part of Pokémon selection UI in for example [**Outbreak Finder**](https://github.com/PokemonAutomation/ComputerControl/blob/master/Wiki/Programs/PokemonLA/OutbreakFinder.md).
To save file transfer and loading time, we usually put all sprites of the entire Pokédex into a single image, like [MMOSprites.png](https://github.com/PokemonAutomation/Packages/blob/master/SerialPrograms/Resources/PokemonLA/MMOSprites.png).
To know which part of the image belongs to which slug (see the [slug topic page](Slug.md) for what a slug is), we need to have an accompanied JSON file to specify this, like what's in [MMOSprites.json](https://github.com/PokemonAutomation/Packages/blob/master/SerialPrograms/Resources/PokemonLA/MMOSprites.json).

## Code to Load JSON 

See code in [Pokemon_PokemonSlugs.cpp](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/Pokemon/Resources/Pokemon_PokemonSlugs.cpp) on how to load a simple JSON of a list Pokémon slugs to get the national Pokédex. 

JSON files for image sprites are more complex. You can learn more on our JSON loading and parsing functions by studying the code that loads image sprites in [`SpriteDatabase`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/CommonFramework/Resources/SpriteDatabase.cpp) class. This `SpriteDatabase` class is used to load an image and its corresponding JSON file to get all the sprites from the image. For example, in [PokemonLA_PokemonMapSpriteReader.cpp](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Inference/Map/PokemonLA_PokemonMapSpriteReader.cpp), `SpriteDatabase` is created to load MMOSprites.png and MMOSprites.json mentioned above.

