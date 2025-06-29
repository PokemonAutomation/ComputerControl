# Exception

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

We have a custom exception [`OperationFailedException`](https://github.com/PokemonAutomation/Arduino-Source/blob/main/Common/Cpp/Exceptions.h) to abort a program.
This is very handy when we detect an error and wish to stop the program right now and display an error message to user.
Many programs use this mechanism.
One example is [**PokemonLA_DistortionWaiter**](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Source/PokemonLA/Programs/General/PokemonLA_DistortionWaiter.cpp).