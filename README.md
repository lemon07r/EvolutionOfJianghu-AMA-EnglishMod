
## Evolution of JiangHu (大衍江湖) - Amateur Modding Avenue Translation Mod V2
### About
This is a fan made translation mod project for the game, 大衍江湖 - Evolution of JiangHu. This mod is an unofficial English translation of the game. This is the new V2 version of the mod, which requires a lot less maintenance than the last mod, and in theory will support future updates of the game a lot more easily.
### Where to get the game?
This early-access game is available on steam here: https://store.steampowered.com/app/1502040/__Evolution_Of_JiangHu/ See this store page for more details about the game. Note that they do not officially support English or this fan-made mod.  
### Community and Support
This mod was brought to you by the Amateur Modding Avenue group, which is a fairly active discord community focused on amateur fan translations of similar games (usually Wuxia, or Xianxia themed Chinese games) and other discussions not limited to just these games. 

If you need any support or assistance please seek us out at our discord server: https://discord.gg/q4zfG6J5gG 

Feel free to visit us even if it's just to hang out, everyone is welcome.

We are also looking for volunteers to help out with this mod and some of our other projects! Let us know if you're interested in helping out. 

For this game in particular we are looking for guide writers, and others to help maintain this mod. Anyone can help out with the guides or submit their own on the discord, we appreciate anything anyone wants to submit, big or small. If you enjoy the game consider sharing with us some of what you know to help out newer players. 

See the ADVANCED section of the mod-tools branch readme if you are interested in helping maintain this mod or just want to compile the mod yourself from your game files. You can do this in the event the current mod release doesn't support your current game version: https://github.com/lemon07r/EvolutionOfJianghu-AMA-EnglishMod/tree/mod-tools#readme
### Credits
- Cadenza - Original Mod Creator
- rfc_club - Mod Template Creator
- Beast - Translated Textures Creator, and Troubleshooting
- Sennek - Mod Creation Help
- Sweetbro - IWOL Replacer Creator (tool used for creating this mod)
- Lamim (lemon07r) - Current Mod and Github Maintainer
- Everyone else at the Amateur Modding Venue discord for any help or support they might have provided

If I missed anyone, please let me know. 
### Downloads
You can download the latest version of the translation mod from this GitHub repo's releases page, our google drive link, or by downloading a zip of this repo's current-release branch. Find the download links below.

https://github.com/lemon07r/EvolutionOfJianghu-AMA-EnglishMod/releases

https://github.com/lemon07r/EvolutionOfJianghu-AMA-EnglishMod/archive/refs/heads/current-release.zip
### Installation Instructions
Switching to the stable branch from the default branch is mandatory as of now to use this translation mod. We currently only support the Stable branch of the game. This game's developer has kindly agreed to update this branch to the latest version for us monthly, which will help keep updates predictable both for maintenance and you guys. Follow the instructions below and see how to change your game to the stable branch.
#### OPTIONAL - Switching your game to the Stable branch
This is no longer mandatory, this new v2 mod will theoretically work with any version of the game. Stable branch updates less frequently.
1. Open Steam and go to your Steam library. Install the game if you haven't yet, then right-click on it and select "Properties" 
2. In the left panel of the properties window select "BETAS" 
3. There will be a drop-down menu under "Select the beta you want to opt into:". Click the drop-down arrow to the right and select "stable - Stable branch" 
4. That's it. You're now on the stable branch of the game and can proceed to follow the instructions below to install the translation mod. 
![Switching to Stable Branch Demonstration](https://i.imgur.com/70yoood.gif)
#### Mod V2 Installation and Information
*More beginner friendly instructions coming soon.*

This is probably the biggest update we've ever had for this mod. All credits to Cadenza, and the others that helped with this mod (rfc_club for the template, Beast for help troubleshooting bugs, etc).

This new mod should work better with updates since in theory it will work with any version of the game. It will patch and generate the translated DLLs for you in a very automated and straight forward process.

CAUTION - There will be bugs. Cadenza has found and fixed as many as he could before greenlighting this release but we still need a lot more testing and feedback from you guys! Find more info on how the mod works and how to use it below, straight from the mod maker himself, Cadenza. I will be working to make a simpler more beginner friendly guide in the future. 

IMPORTANT - This mod breaks old saves because some untranslated stuff gets hardcoded into the save for some reason. We also need help improving the translation since a lot of old manual translations had to be removed for MTL because of a lot of big changes from the developer. 

Important files and procedure :

The translation dict file used to patch the .dll file (hereafter DLLKV) is in BepinEx\plugins\Translations\DLLKV.txt
The translation dict file used to patch the TextAssets file (hereafter TAKV) is in BepinEx\plugins\Translations\TA.txt

If you need to update DLLKV, then, you need to modify this file, same goes for TAKV.

In BepinEx\plugins\Translations\Log, you will find useful informations to update the mod. 

	=>> Update procedure for DLL Patching : 

Everything is automatic. The code will fetch strings from DLLKV, put them in a dict, patch the .dll. 
Anything that is untranslated (string found in the .DLL but not in DLLKV, will be added to Log\DLLUN.txt. 
Anything that is obsolete (i.e. is in DLLKV but not in the .DLL file) will be removed.
Resulting new DLLKV (= DLLKV - Obsolete) will be in Log\NewDLLKV.txt

So if you want to update the KV, you need to : 

Take this NewDLLKV file, translate DLLUN.txt, add it and its translation (with a "¤" separator as always) at the end of NewDLLKV.txt. Rename the file to DLLKV.txt and copy it to the "Translations" dir, overwrite the old file. 

	=>> Update procedure for TA Patching : 

Same than before, there are 3 files : 
Translations\TAKV.txt
Log\NewTAKV.txt
Log\TAUN.txt

To update the TA, you need to have clean files in steamapps\common\大衍江湖\EvolutionOfJiangHu_Data

In-game, press F10. 
TAKV will be used to patch the assets, TTAUN and NewTAKV will be generated.
The generated files will be :

大衍江湖\EvolutionOfJiangHu_Data\resources.assets.modded
大衍江湖\EvolutionOfJiangHu_Data\sharedassets1.assets.modded

We can't have the game replace them directly because they are loaded by the game when it starts, so they can't be modified before the game is exited.

So when it's done (approx 2-4 min), exit the game. Backup your resources.assets and sharedassets1.assets files, rename the .modded files by removing the ".modded" part of their name (so they match the name of the original files).

Relaunch the game. 
