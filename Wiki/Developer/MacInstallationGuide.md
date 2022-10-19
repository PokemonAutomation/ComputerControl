# Guide for Installing SerialPrograms on Mac

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

Guide for how to install our open-source Pokémon automation software, **SerialPrograms** on Mac. This works for both Intel CPU and M1. Note we don't have optimization for M1 yet. So running on M1 macbook could be much slower.

The guide involves some program development processes.
But the guide is aimed for any Mac user. You don't need to know programming to follow the guide.

If you have any questions regarding the documentation or find any errors in the doc, feel free to contact us directly in [our Discord server](https://discord.gg/cQ4gWxN).

Warning: if you don't have software development experience and deviate from the guide steps, you are at your own risk.

### Install XCode App

Go to Mac App Store App, install XCode App. This is a program made by Apple for software development. It also comes with basic software tools to build **SerialPrograms**. So it's safe to install it first.

### Install Homebrew

[Homebrew](https://brew.sh/) is a Mac software that manages software packages. **SerialPrograms** relies on several other open-source software components (called libraries, or packages by software developers). Homebrew is a tool to download and manage those packages.

To install it, the instruction on Homebrew [home page](https://brew.sh/) is to use the command:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Note: if the current Homebrew home page has a different instruction than the one above, follow that from the home page. If you don't know how to do that, contact [us]((https://discord.gg/cQ4gWxN).

The command above is to be executed in the Terminal App. macOS comes with Terminal App.
Launch Terminal App, paste the command inside, press Enter on the keyboard to execute the command.

Apps like Terminal are often shown in movies and shows as what hackers work with on their computers.
If you haven't used one before, be extra careful!
The command you put into Terminal may end up deleting your files without easy way to recover or even destroy your macOS!
Only execute the commands in this guide in Terminal.

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

Note: if the prompted text after installation finishes has a different set of commands than the one above, follow that from your Terminal.
If you don't know how to do that, contact [us]((https://discord.gg/cQ4gWxN).

You can verify Homebrew installation is successful by executing `brew help` in Terminal.
You should see a screen of `Homebrew` instruction shows up like
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

Note: you can scroll up and down in Terminal to see texts outside of the current screen.

### Install CMake

CMake is a software tool that helps compile programs. Install it using Homebrew by running in Terminal
```
brew install cmake
```

Note: if you type a wrong letter in Terminal, press Delete key to delete it, or press Control-C to void the entire line and start with a new line to input command.

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
Contact [us]((https://discord.gg/cQ4gWxN) if you have questions when installing other languages.

### Install OpenCV

OpenCV is a software package for various computer vision algorithms. We need it for using advance video inference methods. Install it by running in Terminal
```
brew install opencv
```

### Download Codebase

Go to **SerialPrograms** Github [webpage](https://github.com/PokemonAutomation/Arduino-Source).
There's a green button "Code". Click it to show download options.

If you know how to use Git to download it, you can use Git. Otherwise, download it as a ZIP file.
Place the code into a suitable folder you like. But avoid placing it in a "remote/cloud" folder like in OneDrive. Cloud folders may give some trouble for programs running on those folders.
If you download as a ZIP, unzip it to a suitable folder.

The downloaded code should be in a folder called "Arduino-Source".

Click the folder to select it in Finder App. Command-C to copy the folder, then go to Terminal, type `cd`, followed by a Space key, then Command-V to paste the folder. It actually paste the folder path in macOS file system to the Terminal. So you would have
```
cd <YOUR_PATH_TO_ARDUINO-SOURCE_FOLDER>
```
in your Terminal. Press Enter to execute it. 

`cd` command moves the current active folder in Terminal to a new folder. Now your Terminal are running on "Arduino-Source" folder. Verify this by executing
```
ls
```
in Terminal. It will list the files and folders in "Arduino-Source" folder.

### Download Program data

**SerialPrograms** need some extra data to run.
Go to our [Packages Github webpage](https://github.com/PokemonAutomation/Packages) and download the data same as before.

The downloaded data will be inside a folder called "Packages". Inside it there is a sub-folder called "SerialPrograms". Further inside is a sub-sub-folder "Resources". Move this "Resources" folder into the "Arduino-Source" folder you downloaded before. Make sure it is placed directly inside "Arduino-Source", not deeper into the folder hierarchy.

### Configure Program

Execute the command in Terminal:
```
mkdir build_mac; cd build_mac
```
This makes a new folder called "build_mac" in "Arduino-Source" and move the Terminal's current active folder to the new folder.

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

Execute the command in Terminal:
```
cmake --build . -j 10
```
to compile and build the program in "build_mac" folder. If successful, it will print 
```
[100%] Built target SerialPrograms
```
in the end in Terminal.

Now **SerialPrograms** is built! Run the program in Terminal by the command
```
./SerialPrograms
```

Enjoy shiny hunting!






