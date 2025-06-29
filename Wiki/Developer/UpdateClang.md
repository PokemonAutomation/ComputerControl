# Update Clang on macOS

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)

If your Clang version is too low you may not be able to compile our automation program without error.

By executing the command in Terminal:
```
g++ --version
```
You should see the information of your current active Clang. An example output is:
```
Apple clang version 14.0.0 (clang-1400.0.29.102)
Target: arm64-apple-darwin21.6.0
Thread model: posix
InstalledDir: /Library/Developer/CommandLineTools
```
The exact version, target and installed directory may be different on your machine.
But as long as your Clang version is higher than 13.0.0, you should be fine to compile our programs by continuing the [guide](MacInstallationGuide.md#verify-clang-version).

### Change Clang Path

If the version is not that high, you can first check if you already have a higher version Clang available somewhere, which may be installed by your most recent XCode App or Homebrew installation.

There are two possible folders where Clang is installed:
```
/Library/Developer/CommandLineTools
```
and
```
/Applications/Xcode.app/Contents/Developer
```
If your `InstalledDir` is one of the two folders, you should check the other. If your `InstalledDir` is neither of them, check both.



To check "/Library/Developer/CommandLineTools", in Terminal, execute
```
ls /Library/Developer/CommandLineTools
```
This `ls` command checks the content of the folder.
If it successfully gives the content of the folder, sth. like
```
Library SDKs  usr
```
Then you have Clang installed there.

To check "/Applications/Xcode.app/Contents/Developer", in Terminal, execute
```
ls /Applications/Xcode.app/Contents/Developer
```
If it successfully gives the content of the folder, sth. like
```
Applications  Library   Makefiles Platforms Toolchains  Tools   usr
```
Then you have Clang installed there.

To switch the current active Clang from the current one to another one, in Terminal, execute
```
sudo xcode-select -s <the folder path>
```
where you fill in `<the folder path>` with the one of the two Clang paths you wish to switch to.
This command will ask for your macOS password. Give the password to let your Mac change compiler.

After it finishes execution, try checking the Clang version again by
```
g++ --version
```
If the version reaches requirement, then you are fine to compile our programs by continuing the [guide](MacInstallationGuide.md#verify-clang-version).

### Update Software

If neither Clang available in the two paths above has high enough version, you can try:
- See if you can update your XCode App on App Store.
- See if you have software upgrade available from System Preferences App -> Software Upgrade.
- See if you can run `xcode-select --install` on Terminal to try installing Clang again.

If you can update and finish the updates, try the steps in the [last section](#change-clang-path) again.

If all of those failed, please reach out to us in [our Discord server](https://discord.gg/cQ4gWxN) for help.

[Back to Mac installation guide](MacInstallationGuide.md)