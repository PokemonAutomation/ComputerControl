# Beginner Guide for Using Github to Contribute

We use Github to host our codebase and allow open-source development. This guide is for developers who know a little bit of Git but don't know how to use it and Github to contribute to an opensource Github project, or for developers who want to refresh the knowledge of Github development.

To complete a feature, we use the standard Github development cycle:
- Fork the [Arduino-Source](https://github.com/PokemonAutomation/Arduino-Source/tree/main/SerialPrograms/Source) repository (repo for short) so that you have a complete copy of the codebase repo under your own Github account.
- Clone your copied repo to your local machine. Make sure your downloaded local repo is linked to your online Github repo.
- Build the **SerialPrograms** executable using CMake, Visual Studio, VS Code, QCreator or other tools.
- Some of the automation programs listed in the **SerialPrograms** require additional resources in the form of files in a folder named `Resources`. You can download the folder from our latest [program releases](https://github.com/PokemonAutomation/ComputerControl/releases) or from the Github repo [Packages](https://github.com/PokemonAutomation/Packages).
Place the `Resources`folder at the same folder hierarchy as the folder of the built **SerialPrograms** executable, so that when launching the executable it can find the resource folder correctly. For example, if the path of **SerialPrograms** is `C:\git\Arduino-Source\build\SerialPrograms.exe` then the resource folder should be `C:\git\Arduino-Source\Resources`.
- Make a new Git branch on your local machine. You can name the branch by the name of the new feature you would like to implement.
- Add commits of new code change to the branch.
- Test the code of this branch to make sure it works and it won't cause problems when merged to the Git trunk (aka main branch) of the codebase.
- Push (aka upload) this branch from your local machine to your Github repo.
- On Github, send a pull request (PR for short) to notify our repo maintainers that a feature development is ready for review.
- The repo maintainers review the new code in the branch, comment on it and give some suggestions if needed.
- Discuss and take those suggestions if needed by improving the code on your local machine. Then push them to update the PR. This may take several rounds of back and forth.
- The repo maintainers approve the feature branch, adding the code into the original repo.

There are many online resources on how to use Git and Github. Feel free to study them if you are not familiar with them.

# Q&A

## Why create a new branch on local machine?

To have the repo maintainers reviewing your changes, you need to have your new code in a PR. A PR is like a post you sent to the maintainers, which lists all your code changes and optionally your comments about them. Both you and the maintainers can comment under the PR, like you commenting under an internet post. To create a PR, you need to associate a branch to it. Therefore you need to create a new branch on your local machine, push (aka upload) it and link it to a PR. You automatically link a PR to the branch when you click a "Create a PR" button on your Github repo for a particular branch you pushed to Github.

Why not use the default branch that is created when initializing my local repo on my local machine? Because the default branch is often the main branch, which serves as the "base": where the code is without your new change. You don't want to add change to this main branch, destroying the content of what the code is before your change.
This is also a good habit of making a separate branch for your changes. If you would like to work on two features at the same time, with two branches you can separate the changes cleanly, reducing your mental load. And you never know when something may happen during developing that forces you to write a new feature. Having all your changes in separate branches keep you clean so that you can easily add a new feature on a new branch that is forked from the main branch, without worrying about prior local changes.