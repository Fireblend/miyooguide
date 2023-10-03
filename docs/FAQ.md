---
title: FAQ + Tips and Tricks
layout: default
nav_order: 6
---
# FAQ / Tips and Tricks
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Adding More Games
Once Onion has been set up, you’ll find a `/Roms/` folder inside your SD card. Inside that folder there's one sub-folder for each console you have activated through the Package Manager - [see here for a quick reference sheet on which folder corresponds to which console](https://github.com/OnionUI/Onion/wiki/Emulators#rom-folders---quick-reference).

You can just drop individual ROM files inside the right folder. So if you want to add a GBA game, you'd add the file to the `/Roms/GBA` folder. Afterwards, safely eject and re-insert your SD card, turn on your Miyoo Mini and press `SELECT` to refresh the ROM lists.

### I can’t see my games!
* Make sure you pressed `SELECT` on the main Onion screen to refresh your ROMs.
* Double check your files are in the correct location by using the Miyoo’s File Browser app.
* Sometimes there are rendering issues in the game list that “hide” the games despite them being there; try “scrolling down” and seeing if they show up by being highlighted.
* Make sure the file type of the games you added by checking against the [Onion Wiki](https://github.com/OnionUI/Onion/wiki/Emulators). For example, Game Boy games must have one of the following extensions: `.bin` `.gba` `.zip` `.7z`

* If you have a `miyoogamelist.xml` file in a console folder (i.e. `/Roms/GBA`), that may prevent new ROMs you added from showing up in the list. Try renaming or removing it and trying again. See [here](https://github.com/OnionUI/Onion/wiki/Frequently-Asked-Questions-%28FAQ%29#how-can-i-use-a-miyoogamelistxml-to-customise-game-names) for more details on that file.

## Fixing Arcade ROMs
Some of the Arcade roms included in the Tiny Best Set romset will not work with the default core included with Onion. In order to fix them, download and install the Arcade Fix in the same way you did for the TBS. There’s a link to the Arcade Fix in the same Internet Archive page from which the TBS is downloaded.

## Enabling Rewinding
Some consoles need to have rewinding enabled before you can use it. Press `Select`+`Menu` to bring up the RetroArch menu, select `Rewind` and toggle on `Rewind Support`. I recommend modifying how often each state is created (`Rewind Frames`) to every 20 frames or so.

To save this at the Core/Emulator level, press `B` to get back to the main menu, then select `Overrides`, then select `Save Core Overrides`.

To use rewind, press `Menu`+`L` while playing.

## Disabling Game Auto-Resume
Some people dislike how Onion auto-resumes their games upon starting them. You can turn off auto resume on the RetroArch settings, then save a core-specific configuration file.

Press `Select`+`Menu` to bring up the RetroArch menu, press `B` to go one menu back, select "Saving" and toggle off `Load State Automatically`.

To save this at the Core/Emulator level, press `B` twice to get back to the main menu, then select `Quick Menu`, then select `Overrides`, then select `Save Core Overrides`.

To just save this setting for a single game select `Save Game Overrides` instead of the above and it will only apply to the game you're currently playing.

## Disabling Save Slot Auto-Increment

Some people dislike how Onion auto increments the save slot by default everytime a quick save is performed, keeping up to the 10 most recent saves. Follow the steps below to disable this:

From the Onion main menu, go into `Apps` > `RetroArch`, select `Saving` and toggle off `Increment Save State Index Automatically`. To save this, press `B` twice, go into `Configuration File` and press `Save Current Configuration`.

If you followed the steps above it might come in handy to know you can switch the active slot in the middle of a game by pressing `Menu`+`Left` and `Menu`+`Right` on the D-Pad. This will decrease and increase the current slot by 1 respectively, and will decide what slot gets used when quick saving and loading.

## Transferring Save-States and Save Files To/From Other Devices
You can transfer your save states and save files to and from other devices just by managing the `/Saves/CurrentProfile/saves/` (for regular in-game saves) and `/Saves/CurrentProfile/states/` (for save states) directories. As long as you’re using the same RetroArch core on your other device, or a core that uses the same save/state format, you can resume games started on your Miyoo, PC or other device in another without any issue. It might also be a good idea to regularly back these directories up. Remember RetroArch names these files the same as the ROMs, so make sure the names match so RA can recognize them.

## Adjust Vibration Intensity
You can adjust the intensity of in-game rumble by going into `Apps` > `RetroArch`, then selecting `Settings` > `Input` > `Haptic Feedback/Vibration` and setting the `Vibration Strength` value to the desired value. To make this change permanent, press `B` twice, go into `Configuration File` and press `Save Current Configuration`.

## Managing Files Through Wi-Fi
You can add games or manage the files on your SD card wirelessly using Onion. You can find details over at the [Onion wiki](https://github.com/OnionUI/Onion/wiki/Samba-filesharing) if you’re on Windows. That link refers to the Samba net-share option because I find it to be the easiest to use, but there are others such as the [HTTP Server](https://github.com/OnionUI/Onion/wiki/HTTP-fileserver). **You need to have an active Wi-Fi connection to access these features.**

On Mac OS, from the Finder menu, click `Go to Server`. In the prompt, enter the IP address prefixed by `smb://` then click `Connect`. You’ll need to provide the credentials specified in the link above.

If you’re on Android, I recommend using [MiXplorer](https://mixplorer.com/) to connect to the Samba share; just create a new Storage by pressing the + button, choose type `LAN (Samba)`, input the Miyoo’s IP address and use the same credentials as those detailed in the link above to access the net share. After this it will be saved as a new location and you won’t have to input the credentials again (unless the device’s IP changes).

On iOS, you can simply use the native `Files` app to access the net share by using the `Connect to Server` option in the three-dots menu within the app and inputting the Miyoo’s IP address. You’ll also need to provide the credentials specified in the Onion wiki link above.

## Switching Between Aspect Ratios
In applicable consoles, press `Start`+`Menu` to switch between different available aspect ratios while in-game. **Check the Onion Shortcuts page** linked below for more shortcuts.

## Using Romhacks
Romhacks are modifications created by the community that are applied on top of a specific ROM to produce a new version of said ROM, with improvements, changes in mechanics, or even new levels and other content altogether.

You can find prepatched ROMs for some of the more popular romhacks if you know where to look, in which case playing them is just a matter of dropping them into the appropriate subfolder in your SD card's `roms` folder.

However, it's also common to find them as patch files (such as the ones you can download from [romhacking.net](https://www.romhacking.net/), with extensions such as `.ups`, `.ips`, etc). **These files need to be combined with a "clean ROM" in order to produce the modified ROM**, using a tool like [romhacking.net's online patcher](https://www.romhacking.net/patch/). Just provide the base ROM as well as the patch file, download the result and you're good to go!

## Tidying Up CD games (PSX, Sega CD, PCE-CD)
If all your CD-ROM games come from the Tiny Best Set, then you’ll notice there’s usually only one `.ch`d file per game in the `PS`, `SEGACD` and `PCECD` directories. This may not be the case if you end up acquiring new ROMs, which tend to come in multiple files; one `.cue` and one or several `.bin` files. It’s strongly recommended to turn these files into one single .chd file, first of all because it’s tidier that way, and secondly these files are compressed and will use much less space than keeping the games as multiple files. To do so, you can use [CHDMAN](https://wiki.recalbox.com/en/tutorials/utilities/rom-conversion/chdman). Instructions in the link.

## Adding Onion Themes
Add themes to your Onion installation by downloading them off of [the official theme repository](https://github.com/OnionUI/Themes), extracting them and placing them on the `Themes` directory in your SD Card's root, then going to `Apps` > `Theme Switcher` in Onion. More details at the repository link.

## Using Overlays
You can add overlays and filters on top of your displayed games. To do so, press `Select`+`Menu` to bring up the RetroArch menu, select `On-Screen Overlays` and toggle on `Display Overlay`. Then select `Overlay Preset` on the same screen, and browse until you find the one you want to apply.
To save this at the Core/Emulator level, press `B` to get back to the main menu, then select `Overrides`, then select `Save Core Overrides`. To just save an overlay for a single game select `Save Game Overrides` instead and it will only apply to the game you're currently playing.

### Additional Overlay Packs
* Dim, subtle frames pack; includes installation+use instructions that apply to all these: 
* [https://github.com/drkhrse/drkhrse_miyoo_bezels](https://github.com/drkhrse/drkhrse_miyoo_bezels)
* Pokémon Themed: 
[https://www.reddit.com/r/MiyooMini/comments/13kdin9/custommade_pokemon_gbgbc_overlays_v2_link_in/](https://www.reddit.com/r/MiyooMini/comments/13kdin9/custommade_pokemon_gbgbc_overlays_v2_link_in)
* Overlays by Tofu:
[https://github.com/jStimpert0430/TofuOverlays](https://github.com/jStimpert0430/TofuOverlays)
* Super Game Boy overlays by Jazqa: [https://www.reddit.com/r/MiyooMini/comments/1616xs3/i_adjusted_all_825_sgb_borders_as_gbgbc_overlays/](https://www.reddit.com/r/MiyooMini/comments/1616xs3/i_adjusted_all_825_sgb_borders_as_gbgbc_overlays)

## Nintendo DS Emulation with DraStic
### Current Version: 1.2 + Audio Patch
A recent addition to the Miyoo Mini ecosystem, the DraStic emulator can be installed on your Miyoo Mini (Regular or Plus) to run DS games. 

{: .warning }
Be aware that performance will vary from game to game and audio lag and glitches are to be expected. Also, you’ll have to source your DS Roms yourself.

In order to install DraStic, create a new `NDS` folder under the `Roms` directory and then place your Nintendo DS ROMs there. Then download and extract [the file from this link](https://github.com/steward-fu/archives/releases/download/miyoo-mini-plus/drastic-v1.2.zip) and put the `drastic` directory under the `Emu` directory of the SD card. Check out the [Readme](https://cdn.discordapp.com/attachments/1063196114448289792/1155154309831479306/readme.pdf) provided by the developer as well.

{: .note }
Don’t use FTP to transfer these files, as people have been having trouble using the emulator when using that protocol.

You should end up with two new locations in your SD card:

* `SDCARD/Emu/drastic/<a bunch of files here>`
* `SDCARD/Roms/NDS/<your DS Roms here>`

There's also an audio patch available to improve audio performance significantly. In order to use it, download [this zipfile](https://cdn.discordapp.com/attachments/1063196114448289792/1156251671886827603/nds_sound_test1.zip?ex=6514f388&is=6513a208&hm=220dab5def0c3ff3ba198a8c08151059bdad1b9c0ed5f6ac84a4ac208fda3f25&) and replace the `libasound.so` and `libasound2.so` files within the `SDCARD/Emu/drastic/libs` directory with the new versions included in the zipfile.

Afterwards, you can access DraStic from the Games section of the Onion main menu. While playing a game, press `R2` to switch screens. Press `L2` to toggle Stylus mode. Press `START`+`SELECT` to switch between screen layouts. Press `MENU` to enter the DraStic menu, from which you can manage save states, change the screen layout and exit the emulator among other things.