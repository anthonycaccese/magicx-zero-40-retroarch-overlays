![promo-image](https://github.com/user-attachments/assets/9b889edc-90f8-457c-b804-c3802ac050ef)

# Magicx Zero 40: RetroArch Overlays

A collection of overlays to be used with RetroArch created specifically for the 3:5 (480x800) screen on the Magicx Zero 40.  

There are 2 initial goals for this collection:

1. Easy to drop-in to an existing RetroArch folder without the need for any additional configuration.
2. Provide custom overlay images that fill the unique vertical 480x800 screen of the Zero 40

---

> [!NOTE]  
> This collection currently only includes vertical ("tate") arcade games but if there is interest in helping to contribute it could be extended support horitzontal aracde games as well as consoles and handheld systems too.

Current status (*as of 7/15/25*):

- Folder Structure: Defined the foundational structure and added support for the FinalBurn Neo core as a first test (more details described in the Usage section below)
- Arcade Configuration: Contains a full list of cfg files for all games marked as "vertical" from the Arcade Database @ [http://adb.arcadeitalia.net/](adb.arcadeitalia.net)
- Arcade Overlay Images: Added a default image named `_vertical-overlay.png` as a foundation for all existing games so that they will display something until more game specific images are created.  Some game specific images have been created to test how game specific images will work.

## Usage

> [!NOTE]  
> The current collection will work with the `FinalBurn Neo` core and all arcade games marked as `vertical` from the Arcade Database @ [http://adb.arcadeitalia.net/](adb.arcadeitalia.net).  Adding additional core support and game support is totally possible but will rely on contributions.  If you are interested in helping out please check the Contribute section below.

1. Download the collection by clicking the `<> Code` button above and selecting `Download ZIP` in the menu that displays.
2. Unzip the file.
3. Copy the `overlays` folder to your RetroArch folder on your android device located at `/storage/emulated/0/RetroArch/`.
	- Note: if you have an existing overlays folder we would recommend backing it up and then try to merge the contents of this folder with your existing one.  That should preserve any other overlays you have in place but there is no way for us to be sure of that.
4. Copy the `config/FinalBurn Neo` folder into your RetroArch/config folder on your android device located at `/storage/emulated/0/RetroArch/config`
	- Note: if you have an existing `config/FinalBurn Neo` folder we would recommend backing it up and then try to merge the contents of this folder with your existing one.  If you have created any specific game or core overrides please make sure to merge them with the corresponding cfg file contained in this collection or you will lose your specific changes.

## Contribute

This collection relies on contributions to add coverage for games, systems and cores. Its open for anyone to contribute so based on what you would like to help with please follow along with one of the options below.  If you have any questions please feel free to open an issue.

### Start here

These are the foundations to understand for all types of contribution:

1. Overlay's are made from 2 files and stored in a `RetroArch/overlays/{system}/` directory
	- For example: the game Dig Dug for the arcade system has 2 files in the `/RetroArch/overlays/arcade/` directory:
		- `digdug.cfg`: a simple set of instructions that tell RetroArch how the overlay will display.  See [these instructions](https://docs.libretro.com/development/retroarch/input/overlay/#configuration) for details about what can go in this file.
		- `digdug.png`: a transparent png for the overlay image that will display when the overlay is loaded by RetroArch. Overlay images should be transparent pngs and sized at 480x800 to fit the Zero 40 screen resolution and aspect ratio.
2. RetroArch determines which overlay to load for a given game through a `{name}.cfg` file located in the `/RetroArch/config/{core}/` directory where...
	- `{core}`: should match the name of that RetroArch assigns to the core itself. For example if you are playing a game through the FinalBurn Neo core than the directory RetroArch will look for cfg files is `/RetroArch/config/FinalBurn Neo/`
		- using the Dig Dug example and assuming you are playing it using the FinalBurn Neo core; the cfg file would be located at: `/RetroArch/config/FinalBurn Neo/digdug.cfg`
	- `{name}.cfg`: can either be the name of a specific game if you want to load a game specific overlay or the name of the core you are using to load a global overlay for all games for a given core.
		- This cfg file simply needs to contain a pointer to the overlay cfg file you want to load: `input_overlay = "/storage/emulated/0/RetroArch/overlays/{system}/{name}.cfg"`
		- For example if you want to load a game specific overlay for Dig Dug when its opened by RetroArch this file would contain: `input_overlay = "/storage/emulated/0/RetroArch/overlays/arcade/digdug.cfg"` 

To contribute an update/change to this collection please fork this repo, make your change and then open a Pull Request with your change against this repo.

### Contribute a Core

#### Background

- RetroArch handles the automatic display of overlays through cfg files that organized by Core in its `/config/` directory (you can see an example in this collection already for the FinalBurn Neo core).
- And inside a core directory RetroArch will use game cfg files first and falls back to a core cfg file if a game cfg does not exist.  
- This structure enables us to create per game overlays or system level overlays that apply to all games for a given system.  So please keep this in mind when adding a core

#### Instructions

TBA

### Contribute a System

TBA

### Contribute a Game

TBA

## Credits

- Arcade marquee images sourced from [Screenscraper.fr](Screenscraper.fr) and [Launchbox GamesDB](https://gamesdb.launchbox-app.com/)
- Arcade game names sourced from the Arcade Database @ [http://adb.arcadeitalia.net/](adb.arcadeitalia.net).
