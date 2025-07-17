![promo-image](https://github.com/user-attachments/assets/9b889edc-90f8-457c-b804-c3802ac050ef)

# Magicx Zero 40: RetroArch Overlays

A collection of overlays to be used with RetroArch created specifically for the 3:5 (480x800) screen on the Magicx Zero 40.  

There are 2 initial goals for this collection:

1. Custom overlay images that fill the unique vertical 480x800 screen of the Zero 40
2. An easy to drop-in set of files for RetroArch without additional configuration.

### What's included currently:
- Game specific overlays for 400+ vertical arcade games
- A default overlay for any vertical game without a game specific image
- No manual configuration needed per game
- Video Demo: https://www.youtube.com/embed/ADeqTLlpRzY

> [!NOTE]  
> The current collection will work with the `FinalBurn Neo` core and any arcade games marked as `vertical` from the Arcade Database @ [http://adb.arcadeitalia.net/](adb.arcadeitalia.net).  Adding additional core/game support is possible and will rely on contributions.  If you are interested in helping out please check the Contribute section below.

## Usage

### Before You Start
- RetroArch installed on your Android device
- FinalBurn Neo core installed in RetroArch  
- Games following standard MAME naming convention
- Access to device storage for file management

### Steps

1. Download the collection by clicking the `<> Code` button above and selecting `Download ZIP` in the menu that displays
2. Unzip the file
3. **To install overlay files:**
   - Navigate to `/storage/emulated/0/RetroArch/` on your device
   - Copy the `overlays` folder from the download to that directory
   - Note: If you have an existing `overlays` folder then back it up first and try to merge the folder from the download instead. That should preserve any other overlays you already have in place but please check just in case.
4. **To install core configuration files:**
   - Navigate to `/storage/emulated/0/RetroArch/config/`
   - Copy the `FinalBurn Neo` folder from the download to that directory
   - Note: if you have an existing `config/FinalBurn Neo` folder then back it up first and try to merge the folder from the download instead.  If you have created any specific game or core overrides please make sure to merge them with the corresponding cfg file contained in this collection or you will lose your specific changes.

### Verify
1. Open RetroArch
2. Load a vertical arcade game with FinalBurn Neo
3. The overlay should appear automatically
4. **If an overlay doesn't appear**:
   - In RetroArch Go to Settings > On-Screen Display > On-Screen Overlay
   - Check if "Overlay Preset" shows your game name
   - If that setting is empty: Review the installation steps above again and check that all your paths match
   - If it shows the name of your game: Open the config file and check the path to the overlay file to make sure its pointing to the right location

## Contribute

This collection relies on contributions to add coverage for games, systems and cores. It's open for anyone to contribute so based on what you would like to help with please follow along with one of the options below.

### Start here

RetroArch uses two sets of files for overlays:

**Overlay Files** (located in the `/RetroArch/overlays/` folder):

- `{name}.cfg` - A configuration file telling RetroArch how to display the overlay
- `{name}.png` - The actual overlay image (480x800 transparent PNG)

**Game/Core Configurations** (located in a `/RetroArch/config/{core}/` folder):

- `{core}`: should match the name that RetroArch assigns to the core itself. For example if you are playing a game through the FinalBurn Neo core then the directory RetroArch will look in for cfg files is `/RetroArch/config/FinalBurn Neo/`
- `{name}.cfg` - This cfg file simply needs to contain a pointer to the overlay cfg file you want to load: `input_overlay = "/storage/emulated/0/RetroArch/overlays/{system}/{name}.cfg"`
- You can either create a game specific or a global core configuration in this folder

**Loading Priority:**

1. Game-specific config (if exists)
2. Core-wide config (fallback)

To contribute an update/change to this collection please fork this repo, make your change and then open a pull request with your change to this repo.

### Contribute a Game

To contribute a game overlay please check the following commit for an example of what is required:
[Game Contribution Example](https://github.com/anthonycaccese/magicx-zero-40-retroarch-overlays/commit/bd854d3e58d5c0dda3666652c240d791e478117b)

In the example you'll see the following:

1. A file called `{gamename}.cfg` in the `RetroArch/config/FinalBurn Neo/` directory which contains a pointer to the overlay cfg to load
2. A file called `{gamename}.cfg` in the `RetroArch/overlays/arcade/` directory which contains a simple set of instructions for how the overlay should render in RetroArch
3. A file called `{gamename}.png` which is the image you've created for the overlay.  Please make sure it's 480x800 in size and a transparent PNG.

Once you have the required files created please submit a pull request to this repo with your changes.

### Contribute a Core

Support for additional RetroArch cores can be added. Check back or open an issue if you'd like to help add support for a specific core.

### Contribute a System  

Console and handheld system support is possible. Check back or open an issue if you'd like to help add support for a specific system.

## Current status (*as of 7/15/25*):

- **Folder Structure**: Defined the foundational folder structure and added support for the FinalBurn Neo core as a first test (more details described in the Usage section below)
- **Arcade Configuration**: Contains a full list of cfg files for all games marked as "vertical" from the Arcade Database @ [http://adb.arcadeitalia.net/](adb.arcadeitalia.net)
- **Arcade Overlay Images**: Added a default image named `_vertical-overlay.png` as a foundation for all vertical arcade games so that they will display something until more game specific images are created.  Over 400 game specific images have also been created to test how game specific images will work.

## Credits

- Arcade marquee images sourced from [Screenscraper.fr](Screenscraper.fr) and [Launchbox GamesDB](https://gamesdb.launchbox-app.com/)
- Arcade game names sourced from the Arcade Database @ [http://adb.arcadeitalia.net/](adb.arcadeitalia.net).
