# Guide for Installing SerialPrograms on Mac

## Introduction
Guide for how to install our open-source Pokémon automation software, **SerialPrograms** on Mac. This works for both Intel CPU and M1.

Note we don't have all the optimization for M1 yet. So running on M1 macbook could be a bit slower.

The guide involves some program development processes.
But the guide is aimed for any Mac user. You don't need to know programming to follow the guide.

If you have any questions regarding the documentation or find any errors in the doc, feel free to contact us directly in [our Discord server](https://discord.gg/cQ4gWxN).

Warning: if you don't have software development experience and deviate from the guide steps, you are at your own risk.

## Part 1: Install Pre-requisites
### Install XCode App

This is a program made by Apple for software development. It also comes with basic software tools to build **SerialPrograms**. So it's safe to install it first.

1. Go to Mac App Store App: Click the Apple Logo at the top left of the screen. Click `App Store` to open.
2. Search for XCode in the searchbar. The app should look like this:

<img src="Images/Mac/xcode.png" alt="A photo of the XCode app" width="202" height="81">

3. Click `Get` to install. This may take a while.

### Launch Terminal

The Terminal App comes with MacOS and is the place where commands are executed. We'll be using the Terminal app for the rest of the installation.

1. Open the Spotlight Search tool: Spotlight Search allows you to search your Mac for programs to run. To open, press `Command-Space` or click the Magnifying Glass icon in the toolbar.
2. Search for `Terminal` and press `return`/`Enter`

To run the commands provided in the rest of the guide, simply paste the command into the window and hit `return`/`Enter`

> Note: if you type a wrong letter in Terminal, press Delete key to delete it, or press `Control-C` to void the entire line and start with a fresh new line to input another command.

Apps like Terminal are often shown in movies and shows as what hackers work with on their computers.
If you haven't used one before, be extra careful! Commands in Terminal are powerful and certain commands delete your files or even destroy your MacOS!
Only execute the commands in this guide in Terminal.

### Install Homebrew

[Homebrew](https://brew.sh/) is a Mac software that manages software packages. **SerialPrograms** relies on several other open-source software components (called libraries, or packages by software developers). Homebrew is a tool to download and manage those packages.

To install it, the instruction on Homebrew [home page](https://brew.sh/) is to use the command:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
> Note: if the current Homebrew home page has a different instruction than the one above, follow that from the home page. If you don't know how to do that, contact [us](https://discord.gg/cQ4gWxN).

Follow the prompted texts in Terminal to finish the installation.
- You will need to type your macOS password to give permission to install Homebrew.
- It will ask you to install Command Line Tools for XCode. XCode is the software development program made by Apple. It has some toolsets needed to build **SerialPrograms**. Follow the text guide on Terminal and install Command Line Tools for XCode.
- After installation finishes, the prompted text will say

```
==> Next steps:
- Run these three commands in your terminal to add Homebrew to your PATH:
    echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /Users/<YOUR_MAC_USERNAME>/.zprofile
    echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/<YOUR_MAC_USERNAME>/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
```
Copy each of the three lines of commands (two starts with "echo" and one starts with "eval") into Terminal and press Enter to execute them.
You need to copy one line, press Enter to execute it, then move on to the next line. You cannot execute all three lines in one single copy-paste.
These commands make the installed Homebrew and future packages it will install, accessible in Terminal.

> Note: if the prompted text after installation finishes has a different set of commands than the one above, follow that from your Terminal.
If you don't know how to do that, contact [us](https://discord.gg/cQ4gWxN).

You can verify Homebrew installation is successful by executing `brew help` in Terminal.
You should see a screen of Homebrew instruction shows up like
```
Example usage:
  brew search TEXT|/REGEX/
  brew info [FORMULA|CASK...]
  brew install FORMULA|CASK...
  brew update
  brew upgrade [FORMULA|CASK...]
  brew uninstall FORMULA|CASK...
  brew list [FORMULA|CASK...]
```

> Note: you can scroll up and down in Terminal to see texts outside of the current screen.

## Part 2: Install Packages

### Install CMake

CMake is a software tool that helps compile programs. Install it using Homebrew by running in Terminal
```
brew install cmake
```

### Install Qt6

We use Qt6 software library to build UI (windows, panels, buttons...) for **SerialPrograms**. Install it by running in Terminal
```
brew install qt6
```

### Install Tesseract

We need Tesseract software package to support our OCR (optical character recognition) technique to read texts from images.

Install it by running in Terminal
```
brew install tesseract
```

After installation, the prompted text may tell you that 
```
==> Caveats
This formula contains only the "eng", "osd", and "snum" language data files.
If you need any other supported languages, run `brew install tesseract-lang`.
```
This says currently installed Tesseract can only read English. If your game language is not English,
run in Terminal
```
brew install tesseract-lang
```
to install other languages.
Contact [us](https://discord.gg/cQ4gWxN) if you have questions when installing other languages.

### Install OpenCV

OpenCV is a software package for various computer vision algorithms. We need it for using advance video inference methods. Install it by running in Terminal
```
brew install opencv
```

### Verify Clang Version

Before building the code of the automation program, make sure the software that builds the code into program is up-to-date. This software is called compilers by programmers. Apple provides a compiler called Clang on macOS. Verify its version by executing the command in Terminal:
```
g++ --version
```
You should see the output like
```
Apple clang version 14.0.0 (clang-1400.0.29.102)
Target: arm64-apple-darwin21.6.0
Thread model: posix
InstalledDir: /Library/Developer/CommandLineTools
```
The exact version, target and installed directory may be different on your machine.
But as long as your Clang version is higher than 13.0.0, you should be fine to proceed.

If you find your Clang version is too low, check this [tutorial](UpdateClang.md) to address it.

## Part 3: Download Codebase

### Download SerialPrograms Source Code

Go to **SerialPrograms** Github [webpage](https://github.com/PokemonAutomation/Arduino-Source).

#### Option 1 - Use Git:
If you know how to use Git to download code from Github, you can use Git and pick a release version based on Git branch names. Otherwise, use Option 2

#### Option 2 - Download directly as a zip file:
Otherwise, download code directly as follows.
By default, when you visit this webpage, it lets you download the newest under-development version.
The version may contain automation programs that are not fully developed or have major bugs.
To use one of our stable release versions, first check the version numbers by pressing the dropdown menu currently shown as "main" on the webpage,
on the same row as the green "Code" button.

The dropdown menu shows recent version numbers. You can pick the latest version you find.
Once you select a version, the text of the dropdown menu will be changed from "main" to that version.

<img src="Images/Mac/branch-version.png" alt="A photo of the Arduino-Source branches on GitHub" width="166" height="286">

After that, click the green "Code" button. It will show several download options.
You can pick "Download ZIP" to download the code as a ZIP file.
The code you download will be from the version you picked.
The default ZIP filename will be "Arduino-Source-\<VERSION_NUMBER\>.zip"

<img src="Images/Mac/download-zip.png" alt="A photo of the menu to download the Arduino-Source code as a zip file" width="205" height="185">

Place the code into a suitable folder you like. But avoid placing it in a "remote/cloud" folder like in OneDrive.
Cloud folders may give some trouble for programs running on those folders.
Also avoid placing it in your macOS account's "Desktop" folder or "Documents" folder.
macOS has strict folder access management. It may reject the program from accessing data in those folders.
An example path is
```
/Users/<YOUR_MAC_USERNAME>/games/pokemon/
```
If you download as a ZIP, unzip it to a suitable folder. Double click the .zip file to unzip it.

The downloaded code should be in a folder called "Arduino-Source". Using the above example, the full path of the folder is
```
/Users/<YOUR_MAC_USERNAME>/games/pokemon/Arduino-Source
```


### Download Program Package Files

**SerialPrograms** needs some extra data (images, audio files and Pokémon data text files) to run.
Go to our [Packages Github webpage](https://github.com/PokemonAutomation/Packages) and download the data as a zip file the same as before but you don't need to pick the versions.

Unzip the download and move the `Packages` folder to inside `Arduino-Source`

<img src="Images/Mac/packages.png" alt="A photo of the Resources folder inside Arduino-Source" width="460">

## Part 4: Compile the Program

### Enter source-code folder:

Click the "Arduino-Source" folder to select it in Finder App. `Command-C` to copy the folder, then go to Terminal, type `cd`, followed by a Space key, then `Command-V` to paste the folder. It actually pastes the folder path in the MacOS file system to the Terminal. So you would have
```
cd <YOUR_PATH_TO_ARDUINO-SOURCE_FOLDER>
```
in your Terminal. Press `return`/`Enter` to execute it. 

`cd` command moves the current active folder in Terminal to a new folder that you specify. Now your Terminal is running in the "Arduino-Source" folder. Verify this by executing
```
ls
```
in Terminal. It will list the files and folders in "Arduino-Source" folder.

### Create a folder to host the compiled program:

Make sure the current active folder in Terminal is the "Arduino-Source" folder, then execute the command in Terminal:
```
mkdir -p build_mac; cd build_mac
```
This makes a new folder called "build_mac" in "Arduino-Source" and moves the Terminal's current active folder to the new folder.

### Use CMake to Configure Program:

Execute the command in Terminal:
```
cmake ../SerialPrograms/ -DUNIX_LINK_TESSERACT:BOOL=true -DCMAKE_BUILD_TYPE:STRING=Release -Wall
```
This command uses CMake to configure our code to prepare for compilation. If successful, it should print texts like
```
...
-- Configuring done
-- Generating done
-- Build files have been written to: <YOUR_PATH_TO_ARDUINO-SOURCE_FOLDER>/build_mac
```

### Compile Program

Make sure the current active folder in Terminal is "build_mac", then execute the command in Terminal:
```
cmake --build . -j 10
```
to compile and build the program in "build_mac" folder.
It will take a while to build depending on your computer's speed.

If successful, it will print 
```
[100%] Built target SerialPrograms
```
at the end in Terminal.

We have built the program on our mac computers, so in most cases you won't see any error during building.
But in case your machine has very different hardware or software environment as ours,
and as a result it prints out error messages about the code,
please reach out to us in [our Discord server](https://discord.gg/cQ4gWxN) for help.

## Part 5: Running the Program

Now **SerialPrograms** is built! in the "build_mac" folder, double click the "SerialPrograms" app to open.

If you're opening the program for the first time, MacOS may ask for Camera and Microphone permissions. These are required in order to read video and audio from your capture card. The program does not access your Mac's actual camera and microphone!

<img src="Images/Mac/compiled-app.png" alt="A photo of the compiled SerialPrograms app" width="460" height="218">

### Computer Battery Setting

When you plan to run the program for a long period of time, you need to prevent your Mac from going to sleep.

Go to System Preferences App -> Battery -> select the checker box "Prevent your Mac from automatically sleeping when the display is off".

Enjoy shiny hunting!

---------------------

## Part 6: Upgrading

### Upgrade to Newest Version

To upgrade, in most cases you just need to repeat the process starting at [Download Codebase](#part-3-download-codebase).

> Note: When updating an existing installation you can `cd` into the existing "build_mac" folder. This way, only the files that changed are recompiled, saving you a lot of time!

```
cd build_mac
```
instead of ...
```
mkdir -p build_mac; cd build_mac
```

### Package updating
In rare cases when we add new software library dependencies, just follow the guide to install those new libraries.
If we upgrade our Qt dependency to a higher Qt version, use Homebrew to upgrade it by running the following command in Terminal:

```
brew upgrade qt6
```



<hr>

Guide Written by: jw098

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)






