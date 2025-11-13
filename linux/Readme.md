from [this steam tutorial](https://steamcommunity.com/sharedfiles/filedetails/?id=2967089130)
and [this answer](https://www.reddit.com/r/linux_gaming/comments/1fleuqw/comment/lo3zod9/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)

# TL;DR 
Step 1 – Launch Deus Ex once with Proton

In Steam, right-click Deus Ex: Game of the Year Edition → Properties → Compatibility.

Check “Force the use of a specific Steam Play compatibility tool”.

Pick Proton Experimental (or your preferred Proton build).

Launch the game, let it reach the menu, then quit.

Step 2:

put the Kentie files  in the System folder but first install via protontricks with:

```
protontricks 6910 d3dx10 vcrun2010 dxvk

```

then launch from Steam as non steam game weith compatibility mode proton experimental

## For me the custom launcher didn't work with direct3d 10 but launching the regular game and checking 'show all rendering options' on popup at first run allowed me to check direct3d 10 rendering 

---------
_old, just for reference_

Preliminary Notes

Introduction

**This guide will be** taking you through the steps needed to get the game playing near-flawlessly on modern systems running Linux. The focus is to make it as easy and as digestible, so that _any_ Linux user can follow each step!  
  
**This guide will _NOT_ be** showing how to install complete overhauls or mods that alter the gameplay!  
  
_Below you'll see my distro and machine specifications, and the guide will be going based off of those, as I cannot possibly cover every distro or PC specification setup. So if you are on a drastically different distro and/or machine, you may have to do some googling yourself, to complete the steps in this guide, but I'll do my best to make it as easy for you, as I can._  
  

My System & Machine Specifications

*   **OS:** Arch Linux  
    
*   **KERNEL:** 6.2.11-arch1-1  
    
*   **CPU:** Intel Core i5-4690K @ 3.50GHz  
    
*   **GPU:** NVIDIA GeForce GTX 970  
    
*   **GPU DRIVER:** NVIDIA 530.41.03  
    
*   **RAM:** 16GB @ 2400Mhz

Prerequisites

Basic Requirements

*   Up-to-date Steam copy of Deus Ex (Obviously)  
    
*   Latest drivers for your Linux distro and GPU.  
    
*   Steam's Proton function enabled.  
    
*   Protontricks.  
    
*   Any terminal emulator.

**If you are having any issues, check that you meet all of the requirements above _before_ reporting a problem!**  
  

Enabling Steam's Proton

1.  In your Steam client, go to the top right corner.  
    
2.  Click on 'Steam'  
    
3.  Click 'Settings'  
    
4.  Click on the 'Steam Play' tab.  
    
5.  Tick both boxes.  
    
6.  Select 'Proton Experimental' in the drop-down menu.  
    
7.  Click 'OK'  
    
8.  Done!

  

Installing Protontricks

**If you are on an Arch-based distro:**  

paru -S protontricks

_**OR**_  

yay -S protontricks

  
Either if these commands will download Protontricks from the [Arch User Repository](https://aur.archlinux.org/packages?O=0&amp;K=protontricks)\[aur.archlinux.org\] (or AUR, for short)  
  
**If you are _NOT_ on an Arch-based distro:**  
[Follow the instructions that apply to you here](https://github.com/Matoking/protontricks)\[github.com\]

Mods & Patches

Kentie's Launcher (REQUIRED!)

This simplifies the configuration of the game, by using a different config and save location, and allows us to use a custom renderer, which will further improve the game's performance!  

_

Download:

_*   [Kentie's Launcher](https://kentie.net/article/dxguide/index.htm)\[kentie.net\]

_

Installation:

_2.  First off, we're going to create a 'Downloads' directory in our Home directory, to keep everything organized. Run these commands to do so:  
    
    cd
    
    mkdir Downloads
    
3.  Download the file to:
    
    ~/Downloads/
    
4.  Run the following commands in the written order:  
    
    cd ~/Downloads/
    
    7za x -oKentiesLauncher DeusExe-v8.1.zip
    
    This will extract all files from the archive in a directory called, "KentiesLauncher"  
      
    
    cd KentiesLauncher/
    
    mv deusex.exe DeusEx.exe
    
    We need to use the 'mv' command to rename the .exe since Linux is case-sensitive. This ensures that we're overwriting the original .exe and that Steam uses the correct file.  
      
    
    cp DeusEx.u DeusEx.exe ~/.steam/root/steamapps/common/Deus\\ Ex/System/
    
    Here, we're just copying and overwriting the necessary files in the install directory of Deus Ex, so we can actually use the mod! The directory path above, is the default install directory for Steam--if you have your Steam client and/or your Steam games installed in a different directory, make sure to replace the path above with where your game is installed!  
      
    
5.  Overwrite existing files if prompted.  
    
6.  Done!

  

Kentie's Unreal Engine Direct3D 10 Renderer (REQUIRED!)

This renderer provides graphical improvements (bump mapping, anti-aliasing, anisotropic filtering, unlimited view distance, etc.) and improves the responsiveness of the mouse, and general performance and stability on modern systems!  

_

Download:

_*   [Kentie's Unreal Engine Direct3D 10 Renderer](https://kentie.net/article/d3d10drv/index.htm)\[kentie.net\]

_

Installation:

_2.  Download the file to:
    
    ~/Downloads/
    
3.  Run the following commands in the written order:  
    
    cd ~/Downloads/
    
    7za x -oKentiesRenderer d3d10drv-v29.zip
    
    cd KentiesRenderer/DeusEx/
    
    cp -r d3d10drv/ d3d10drv.dll D3D10Drv.int ~/.steam/root/steamapps/common/Deus\\ Ex/System/
    
4.  Now we need to use Protontricks to install the prerequisites for Kentie's Launcher and the custom renderer. Run the following commands to do so:  
    
    protontricks --gui
    
    It does not matter where you run this command. Protontricks will allow us to install the required drivers for the mods to run on our system.  
      
    
5.  Skip warnings and pop-ups until you see a list of your installed Steam games.  
    
6.  Select 'Deus Ex: Game of the Year Edition: 6910' and click 'OK'  
    
7.  Skip warnings and pop-ups until you see a list of options.  
    
8.  Select 'Select the default wineprefix' and click 'OK'  
    
9.  Select 'Install a Windows DLL or component' and click 'OK'  
    
10.  Find and tick the following packages:  
    *   d3dx10\_43  
        
    *   d3dx10  
        
    *   dxvk  
        
    *   vcrun2010  
        
    *   vcrun2015  
        _**NOTE:** A user has reported that vcrun2015 \*may\* not be needed and can be skipped, if the installation is throwing errors, as is what happened with the aforementioned user._
11.  Click 'OK'  
    
12.  Click 'OK' to all of the following pop-ups.  
    
13.  Follow the installation wizards for the prerequisites.  
    
14.  After the installation is done, you should be returned to the window with a bunch of options. Click 'Cancel' until the program closes.  
    
15.  Done!

  

Deus Ex Unofficial Patch (Optional)

Fixes some old bugs that do not interfere with the gameplay. Optional, but recommended! Install _after_ installing Kentie's Launcher and Direct3D 10 Renderer.  

_

Download:

_*   [Deus Ex Unofficial Patch](https://www.moddb.com/games/deus-ex/downloads/deus-ex-unofficial-patch-v2)

_

Installation:

_2.  Download the file to:
    
    ~/Downloads/
    
3.  Run the following commands in the written order:  
    
    cd ~/Downloads/
    
    7za x -oDeusExPatch DeusExV2.zip
    
    cd DeusExPatch/
    
    cp DeusEx.u ~/.steam/root/steamapps/common/Deus\\ Ex/System/
    
4.  Overwrite if prompted.  
    
5.  Done!

  

Confix Patch (Optional)

Corrects some spelling mistakes in the text and dialogue subtitles all throughout the game. Optional, but recommended!  

_

Download:

_*   [Confix Patch](https://www.moddb.com/mods/confix/downloads/confix-compiled)

_

Installation:

_2.  Download the file to:
    
    ~/Downloads/
    
3.  Run the following commands in the written order:  
    
    cd ~/Downloads/
    
    7za x -oDeusExConfix Confix\_compiled.4.zip
    
    cd DeusExConfix/
    
    cp \*.u ~/.steam/root/steamapps/common/Deus\\ Ex/System/
    
4.  Overwrite if prompted.  
    
5.  Done!

  

Maps Patch (Optional)

Fixes some bugs that are still troubling a lot of the levels to this day. Optional, but recommended!  

_

Download:

_*   [Maps Patch](https://www.dxm.be/navigator.php5?lang=en&amp;content=202)\[www.dxm.be\]

_

Installation:

_2.  Download the .7z archive (_NOT_ the .exe!) to:
    
    ~/Downloads/
    
3.  Run the following commands in the written order:  
    
    cd ~/Downloads/
    
    7za x -oDeusExMaps DeusEx\_MapsPatch13.7z
    
    cd DeusExMaps/
    
    cp -r Maps/ ~/.steam/root/steamapps/common/Deus\\ Ex/
    
4.  Overwrite if prompted.  
    
5.  Done!

  

Speedup Fix (Optional)

This fixes a problem that makes the game literally speed up when running at higher than 200 FPS. This for me, was most noticeable when dialogue would start skipping! You can either limit the max FPS to 200 (or less), or you can use this fix to run the game with uncapped FPS, without any problems! Optional, but of course, recommended!  
  
I will refer you to this guide that describes the issue in detail, and provides a download link for the patch/fix!  
[![](https://community.fastly.steamstatic.com/public/shared/images/sharedfiles/steam_workshop_default_image.png)

Deus Ex Speedup Fix 

A Guide for Deus Ex: Game of the Year Edition

By: You should go Heavy, NOW!

One line of code causes all the problems..... A simple hex edit fixes it.... I will provide a fixed dll for lazy people and go over how to do it yourself.



](https://steamcommunity.com/sharedfiles/filedetails/?id=2048525175)  
The guide does not contain explicit installation instructions, so I will cover that here.  

_

Installation:

_2.  Download the file to:
    
    ~/Downloads/
    
3.  Run the following commands in the written order:  
    
    cd ~/Downloads/
    
    7za x -oDeusExSpeedFix Fixed\_Speedup.7z
    
    cd DeusExSpeedFix/
    
    cp Engine.dll ~/.steam/root/steamapps/common/Deus\\ Ex/System/
    
4.  Overwrite if prompted.  
    
5.  Done!

Settings

**You must follow this step to use the custom renderer and to avoid some common issues!**  

_Part 1:_ Kentie's Launcher Configuration

1.  Launch the game through Steam, and if you did everything correctly, you should see something like this:  
    [![](https://images.steamusercontent.com/ugc/2026099899765328899/0BAA501049C51A8921DD1C3B69E2E13AC8F9674F/)](https://images.steamusercontent.com/ugc/2026099899765328899/0BAA501049C51A8921DD1C3B69E2E13AC8F9674F/)  
      
    
2.  Click 'Configure' and you should see this screen:  
    [![](https://images.steamusercontent.com/ugc/2026099899765335012/5B80AA306EE39BD5075F635121F433A47522E0CA/)](https://images.steamusercontent.com/ugc/2026099899765335012/5B80AA306EE39BD5075F635121F433A47522E0CA/)  
      
    
3.  Set the renderer to 'Direct3D 10 Support'  
    
4.  Change the FPS limit to what you'd like, but do _not_ set it to higher than 200! If you do, the dialogue will start to skip!  
    
5.  Set the viewport to 'Fullscreen' or you might experience some lag/freezing when opening menus.  
    
6.  Adjust all other settings to your liking, click 'OK' and then you're done!

_Part 2:_ Kentie's Custom Renderer Settings

1.  Launch the game by opening the launcher through Steam like before, and click 'Play'  
    
2.  Before pressing any key that makes the main menu show, open the text chat (Default key: T)  
    
3.  Delete 'Say' and write:  
    
    preferences
    
4.  Press 'Enter' and you should see a window pop-up with several drop-down menus. This will let us mess with a bunch of new settings that the custom renderer has unlocked!  
    
5.  Expand the 'Rendering' drop-down menu.  
    
6.  Expand the 'Direct3D 10 Support' drop-down menu.  
    
7.  Change settings to what you'd like! I highly recommend setting 'AutoFOV' to 'False' and 'ClassicLighting' to 'True' so you get the original (and in my opinion superior) original lighting, and you're able to change your FOV without it resetting when you launch the game.  
    
8.  When you're done, click the X in the top right, and let it load. Now you're ready to play!

Additional Configuration

This section of the guide is completely optional. It just allows you to fine-adjust a couple of things.  
  

_Part 1:_ Locating the Config Files

1.  Go to:
    
    ~/.steam/root/steamapps/compatdata/6910/pfx/drive\_c/users/steamuser/Documents/Deus\\ Ex/System
    
    Again, like I said earlier, if you have your Steam client and/or Steam games installed in a different directory, as opposed to the default directory; replace the path above with the correct one that applies to your system!

_Part 2a:_ Reducing the Head Bobbing

1.  Open/Edit 'User.ini' with your preferred editor.  
    
2.  Find:
    
    Bob=
    
3.  Replace the current value with your desired head bobbing strength.

_Part 2b:_ Fine-tuning Mouse Sensitivity

1.  In 'User.ini' find:
    
    MouseSensitivity=
    
2.  Replace the current value with your desired sensitivity.

  
**When you're done making all of your desired changes, write/save and quit the file, and you're ready to play!**

Common Issues & Troubleshooting

As you can guess, if people are reporting any issues they are encountering, they will be listed here, hopefully alongside a way to fix them.  
  

Fixed

1.  **Game lags or freezes when opening menus, such as the inventory.**  
    \- Enable fullscreen in Kentie's Launcher.  
      
    
2.  **Dialogue occasionally skips lines.**  
    \- Limit max FPS to 200 or less in Kentie's Launcher, or refer to the Mods & Patches section of this guide, and use the Speed Fix.  
      
    
3.  **Game is too dark or too bright.**  
    \- Using the custom renderer allows you to change the brightness levels inside the game's options menu.

  

Not Fixed

None yet, fortunately!

Changelog

_Date Format: DD/MM/YYYY_  
  

*   27/04/2023 | Added Speed Fix to the Mods & Patches section + Updated Common Issues & Troubleshooting section.  
    
*   27/04/2023 | Removed unnecessary code-block in favor of legibility.  
    
*   26/04/2023 | Guide published.  
    
*   25/04/2023 | Guide created.

Final Notes

Thank you for taking the time to read my guide! I hope it was helpful to you. If you feel something is missing from this guide, or if you are encountering issues, please leave a comment and I'll get back to you, as soon as I can.  
  

_BEFORE COMMENTING!_

**_Please make sure you have read the guide thoroughly, and done the steps correctly!_**  
  

Additional Resources

*   [PCGamingWiki](https://www.pcgamingwiki.com/wiki/Deus_Ex)\[www.pcgamingwiki.com\]  
    
*   [ProtonDB](https://www.protondb.com/app/6910)\[www.protondb.com\]

  

Credits

[McPorker](https://steamcommunity.com/id/McPorker/) for writing this guide, troubleshooting and testing the game.  
[BinaryWarrior76](https://steamcommunity.com/id/binarywarrior76) for troubleshooting, proofreading and assisting with Protontricks!
