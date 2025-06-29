# ZK-WiiPresenceU-Beta
This project was made strictly for Cemu and it makes it easier for some apps to be displayed onto your discord rich presence mainly the ones that are online with pretendo online 


# Wii Presence U - Beta (1.0)

A modern, user-friendly Discord Rich Presence and cover art UI for Cemu Wii U emulator.

## Features
- Automatic Discord Rich Presence for Cemu and Wii U games
- Custom cover art support for any game (mapped or unmapped)
- Add your own Discord asset names and activity details
- Responsive, robust UI with error handling
- Auto-close when Cemu closes (even if Cemu was started manually)
- Google Images fallback for unmapped games, with image preview and easy saving
- No Python setup required for EXE version—just extract and run
- All config, mappings, and covers are portable and saved alongside the app
- Modern, clean UI with menu bar for advanced options
- Debug info and error log for troubleshooting

## How to Use

### 1. Setup
#### For EXE (Recommended for most users)
- Download the release ZIP from GitHub and extract all files to a folder
- **Navigate directly into the extracted folder** (not a parent folder)
- **Double-click `main.exe` (or `WiiPresenceU.exe` if renamed) to launch the app**
- On first launch, set your Cemu.exe path when prompted

#### For Python Script (Advanced/Developers)
- Download and extract all files to a folder
- Run `main.py` (not `WPU_UI.py`) (requires Python 3.8+, Pillow, pypresence, psutil, requests, beautifulsoup4, pywin32)
- On first launch, set your Cemu.exe path when prompted

### 2. Adding Custom Cover Art & Discord Assets
- Launch a game in Cemu
- If the game is unmapped, the app will automatically search Google Images for possible cover art.
- You can flip through up to 12 image results using the `Next Image` and `Previous Image` buttons directly below the cover art.
- When you find an image you like, click `Save as Discord Asset` to map it for future use.
- After saving, the navigation and save buttons will disappear and the new cover art will be used for both the UI and Discord Rich Presence.
- **Note:** You cannot upload your own custom asset images; only Google Images results can be used for cover art.

### 3. Editing Game Mappings
- You can manually edit `game_mappings.json` to add or change mappings
- Each entry: `[Display Name, Discord Asset Name, Activity/Detail, (optional) Cover Art Path]`

### 4. Using Your Own Discord Application
- Create a new application at https://discord.com/developers/applications
- Add your own image assets (name them as you wish)
- Enter your Client ID in the code (edit `CLIENT_ID` in `WPU_UI.py`)
- Use your asset names when adding custom cover art

### 5. Auto-Close Behavior
- Wii Presence U will automatically close itself whenever Cemu closes, even if you started Cemu manually.
- You do not need to launch Cemu from the app for this feature to work.

## Troubleshooting
- If you see errors, check `wpu_ui_error.log` for details
- You can clear the log by deleting the file

## Building an EXE (for developers)
- Use PyInstaller or similar tool to bundle the app:
  - Example: `pyinstaller --onefile --add-data "game_mappings.json;." --add-data "wpu_ui_config.json;." --add-data "icon.ico;." --add-data "custom_covers;custom_covers" WPU_UI.py`
- Make sure all data files are included in the same folder as the EXE
- The app will automatically find its data files when run as an EXE

## Credits
- Developed by ZK
- Thanks to the Cemu, Pretendo, and Discord RPC communities

---

Enjoy Wii Presence U! For issues or suggestions, open an issue or PR on GitHub.
