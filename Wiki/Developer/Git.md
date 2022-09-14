# Develop Using Github

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

We use Github to host our codebase and allow open-source development. This guide is for developers who know a little bit of Git but don't know how to use it and Github to contribute to an open-source Github project, or for developers who want to refresh the knowledge of Github development. It also contains some tips about building and developing the code.

To add a new feature to the code, we use the standard Github development cycle:

- Fork the [Arduino-Source](https://github.com/PokemonAutomation/Arduino-Source/tree/main/SerialPrograms/Source) repository (repo for short) so that you have a complete copy of the codebase repo under your own Github account.
- Clone your copied repo to your local machine. Make sure your downloaded local repo is linked to your online Github repo.
- Build the **SerialPrograms** executable using CMake, Visual Studio, VS Code, QCreator or other tools.
- Some of the automation programs listed in the **SerialPrograms** require additional resources in the form of files in a folder named `Resources`.
	- You can download the folder from our latest [program releases](https://github.com/PokemonAutomation/ComputerControl/releases) or from the Github repo [Packages](https://github.com/PokemonAutomation/Packages).
	- Place the `Resources`folder at the same folder hierarchy as the folder of the built **SerialPrograms** executable, so that when launching the executable it can correctly find the resource folder.
	For example, if the path of **SerialPrograms** is `C:\git\Arduino-Source\build\SerialPrograms.exe` then the resource folder should be `C:\git\Arduino-Source\Resources`.
- Make a new Git branch on your local machine. You can name the branch by the name of the new feature you would like to implement.
- Before adding commits to the branch, set correct author name and email info in the Git config file. If you want to maintain anonymous, make sure you don't expose your personal info in your Github account and commit messages. Double check you don't set a global author and email info across that could add your personal info on a new Git repo.
- Write the feature code. Add commits of the new code change to the branch.
	- If you add or remove code files in the source-code folder, you need to update the file list in [CMakeLists.txt](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/CMakeLists.txt) and [SerialPrograms.pro](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/SerialPrograms.pro).

	If you know a bit about Python, we have Python helper script [add_new_file.py](https://github.com/PokemonAutomation/Arduino-Source/blob/main/SerialPrograms/Scripts/add_new_file.py) for you to add a new file in those file lists. An example usage:
	```
	python3 Arduino-Source/SerialPrograms/Scripts/add_new_file.py Source/<some_middle_path>/Pokemon_NewFile.h
	```
	This adds the path of Pokemon_NewFile.h to both CMakeLists.txt and SerialPrograms.pro.
- Test the code of this branch to make sure it works and it won't cause problems when merged to the Git trunk (aka main branch) of the codebase.
- Push (aka upload) this branch from your local machine to your online Github repo.
- On Github, send a pull request (PR for short) to notify our repo maintainers that a feature development is ready for review.
- The repo maintainers review the new code in the PR, comment on it and give some suggestions if needed.
- Discuss and take those suggestions if needed by improving the code on your local machine. Then push them to update the PR. This may take several rounds of back and forth.
- The repo maintainers approve the PR about the feature branch, adding the code into the original repo.
- Prepare for developing next feature:
	- After the new code has been added to the original repo as new commits, update the main branch of your online Github repo so receive the new commits as well. 
	- Pull (aka download) those commits into the main branch of your local repo.
	- You can then delete the feature branch.

There are many online resources on how to use Git and Github. Feel free to study them if you are not familiar with them.

# Q&A

## Why create a new branch on local machine?

To have the repo maintainers reviewing your changes, you need to have your new code in a PR. A PR is like a post you sent to the maintainers, which lists all your code changes and optionally your comments about them. Both you and the maintainers can comment under the PR, like you commenting under an internet post. To create a PR, you need to associate a branch to it. Therefore you need to create a new branch on your local machine, push (aka upload) it and link it to a PR. You automatically link a PR to the branch when you click a "Create a PR" button on your Github repo for a particular branch you pushed to Github.

Why not use the default branch that is created when initializing my local repo on my local machine? Because the default branch is often the main branch, which serves as the "base": where the code is without your new change. You don't want to add change to this main branch, destroying the content of what the code is before your change.
This is also a good habit of making a separate branch for your changes. If you would like to work on two features at the same time, with two branches you can separate the changes cleanly, reducing your mental load. And you never know when something may happen during developing that forces you to write a new feature. Having all your changes in separate branches keep you clean so that you can easily add a new feature on a new branch that is forked from the main branch, without worrying about prior local changes.