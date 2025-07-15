![promo-image](https://github.com/user-attachments/assets/9b889edc-90f8-457c-b804-c3802ac050ef)

# Magicx Zero 40: RetroArch Overlays

A collection of overlays to be used with RetroArch created specifically for the 3:5 screen aspect ratio on the Magicx Zero 40.  

The goal is for this collection to be easy to drop-in to an existing RetroArch folder without the need for any additional configuration.  

> [!NOTE]  
> This collection currently only includes vertical ("tate") arcade games but if there is interest in helping to contribute it could be extended support horitzontal aracde games as well as consoles and handheld systems too.

Current status (*as of 7/15/25*):

- Folder Structure: Defined the foundational structure and added support for the FinalBurn Neo core as a first test (more details described in the Usage section below)
- Arcade Configuration: Contains a full list of cfg files for all games marked as "vertical" from the Arcade Database @ [http://adb.arcadeitalia.net/]
(adb.arcadeitalia.net)
- Arcade Overlay Images: Added a default image named `_vertical-overlay.png` as a foundation for all existing games so that they will display something until more game specific images are created.  Some game specific images have been created to test how game specific images will work.

## Usage

> [!NOTE]  
> The current collection will work with the `FinalBurn Neo` core and all arcade games marked as `vertical` from the Arcade Database @ [http://adb.arcadeitalia.net/](adb.arcadeitalia.net).  Adding additional core support and game support is totally possible but will rely on contributions.  If you are interested in helping out please check the Contribute section below.

1. Download the collection by clicking the `<> Code` button above and selecting `Download ZIP` in the menu that displays.
2. Unzip the file.
3. Copy the `overlays` folder to your RetroArch folder on your android device located at `/storage/emulated/0/RetroArch/`.
	- Note: if you have an existing overlays folder we would recommend backing it up and then try to merge the contents of this folder with your existing one.  That should preserve any other overlays you have in place but there is no way for us to be sure of that.
4. Copy the `config/FinalBurn Neo` folder into your RetroArch/Config folder on your android device located at `/storage/emulated/0/RetroArch/config`
	- Note: if you have an existing `config/FinalBurn Neo` folder we would recommend backing it up and then try to merge the contents of this folder with your existing one.  If you have created any specific game or core overrides please make sure to merge them with the corresponding cfg file contained in this collection or you will lose your specific changes.

## Contribute

TBA

## Credits

- Arcade marquee images sourced from [Screenscraper.fr](Screenscraper.fr) and [Launchbox GamesDB](https://gamesdb.launchbox-app.com/)
- Arcade game names sourced from the Arcade Database @ [http://adb.arcadeitalia.net/](adb.arcadeitalia.net).
