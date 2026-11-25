<div align="center">

<img src="https://raw.githubusercontent.com/termux/termux-app/master/app/src/main/res/mipmap-xxxhdpi/ic_launcher.png" width="68" alt="Termux">

# Awesome Termux

**Termux Customization Toolkit · Colors · Fonts · Presets**

A lightweight toolkit to personalize Termux with color presets, custom HEX colors, fonts and backups. No root required.

<img src="https://img.shields.io/badge/Android-Termux-3DDC84?style=flat-square&logo=android&logoColor=white">
<img src="https://img.shields.io/badge/Root-Not%20Required-16A34A?style=flat-square">
<img src="https://img.shields.io/badge/Language-Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white">
<img src="https://img.shields.io/badge/Custom%20HEX-Supported-8B5CF6?style=flat-square">
</div>

---

## Overview

Awesome Termux is an interactive Bash toolkit for customizing the appearance of the Termux terminal.

| Feature | Description |
| --- | --- |
| Color presets | Ready-to-use terminal color schemes |
| Custom colors | Set background, text and cursor using HEX |
| Font installer | Install `.ttf`/`.otf` fonts from HTTPS URLs or local files |
| Backup | Save existing colors and font before changes |
| Restore | Restore the latest saved backup |
| Root access | Not required |

## Requirements

| Component | Requirement |
| --- | --- |
| Device | Android with Termux installed |
| Termux | Current version recommended |
| Packages | `bash`, `curl`, `file` |
| Storage | A few MB, depending on selected font |
| Root | Not required |

> Install Termux and its add-ons from a trusted source. Avoid mixing installations from different sources.

## Installation

### 01 — Update Termux

```bash
pkg update -y && pkg upgrade -y
pkg install git curl file -y
```

### 02 — Download Awesome Termux

```bash
git clone https://github.com/SEU-USUARIO/Awesome-Termux.git
cd Awesome-Termux
```

Replace `SEU-USUARIO` with your GitHub username after publishing the repository.

### 03 — Run the installer

```bash
chmod +x install.sh
./install.sh
```

The interactive menu will open.

## Main menu

```text
===== Awesome Termux =====
1) Presets de cores
2) Cor personalizada
3) Instalar fonte por URL
4) Instalar fonte do armazenamento
5) Fazer backup
6) Restaurar último backup
0) Sair
```

Enter the number of the action you want.

## Color presets

| Preset | Background | Foreground | Cursor |
| --- | --- | --- | --- |
| AMOLED | `#000000` | `#E6E6E6` | `#FFFFFF` |
| Purple Dark | `#0F0B12` | `#E6E1E9` | `#BB86FC` |
| Android Green | `#07140B` | `#E8F5E9` | `#00C853` |
| Dracula | `#282A36` | `#F8F8F2` | `#BD93F9` |
| Nord | `#2E3440` | `#D8DEE9` | `#88C0D0` |

### Apply a preset

1. Run `./install.sh`.
2. Select `1) Presets de cores`.
3. Enter the preset number.
4. Awesome Termux saves a backup and applies the selected palette.
5. The script attempts to reload Termux settings.

If the colors do not update immediately, close and reopen the Termux session.

## Custom colors

1. Run `./install.sh`.
2. Select `2) Cor personalizada`.
3. Enter the background, foreground and cursor HEX values.

Example:

```text
Fundo (#RRGGBB): #0F0B12
Texto (#RRGGBB): #E6E1E9
Cursor (#RRGGBB): #BB86FC
```

Use six hexadecimal digits. The leading `#` is optional.

## Install a custom font

The installer accepts TrueType/OpenType font files (`.ttf`/`.otf`).

### Option A — HTTPS URL

1. Find a direct HTTPS link to a font file.
2. Run `./install.sh`.
3. Select `3) Instalar fonte por URL`.
4. Paste the direct URL.
5. The script checks the downloaded file, backs up the current configuration and installs the font.

Example: JetBrains Mono Regular

```text
https://raw.githubusercontent.com/JetBrains/JetBrainsMono/master/fonts/ttf/JetBrainsMono-Regular.ttf
```

### Option B — Local file

1. Place the font file somewhere accessible to Termux.
2. Run `./install.sh`.
3. Select `4) Instalar fonte do armazenamento`.
4. Enter the full file path.

Example:

```text
/storage/emulated/0/Download/JetBrainsMono-Regular.ttf
```

If shared storage is not accessible, run:

```bash
termux-setup-storage
```

Then grant the requested Android permission.

> **Nerd Fonts:** regular JetBrains Mono does not contain all Nerd Font icons. For Powerlevel10k symbols, install a compatible Nerd Font build.

### Adjust font size

Change the font size using the pinch gesture on the Termux terminal screen. Awesome Termux does not currently set font size through its menu.

## Backup and restore

Backups are stored in:

```text
~/.awesome-termux-backups/
```

Each backup is placed in a date-and-time folder.

### Create a backup manually

1. Run `./install.sh`.
2. Select `5) Fazer backup`.

### Restore the latest backup

1. Run `./install.sh`.
2. Select `6) Restaurar último backup`.
3. The latest saved colors and font are copied back.
4. Termux settings are reloaded when the command is available.

## Configuration files

| File | Purpose |
| --- | --- |
| `~/.termux/colors.properties` | Background, foreground and cursor colors |
| `~/.termux/font.ttf` | Custom terminal font |
| `~/.awesome-termux-backups/` | Saved configuration backups |

Reload settings manually:

```bash
termux-reload-settings
```

If the command is unavailable, close and reopen Termux.

## Troubleshooting

| Issue | Solution |
| --- | --- |
| `Permission denied` | Run `chmod +x install.sh` |
| `git: command not found` | Run `pkg install git -y` |
| Font URL fails | Use a direct HTTPS link to a font file |
| Font is rejected | Check that the file is a valid TTF/OTF |
| Shared storage inaccessible | Run `termux-setup-storage` and grant permission |
| Colors do not change | Run `termux-reload-settings`, then reopen Termux |
| Icons appear as boxes | Install a compatible Nerd Font |
| No backup available | Create a backup before attempting restoration |

## Project structure

```text
Awesome-Termux/
├── README.md
├── LICENSE
├── .gitignore
├── install.sh
├── presets/
└── scripts/
```

## Current status

- [x] Interactive Bash menu
- [x] Five color presets
- [x] Custom HEX background, foreground and cursor
- [x] Font installation from HTTPS URL
- [x] Font installation from local storage
- [x] Backup and restore
- [ ] Zsh / Oh My Zsh integration
- [ ] Powerlevel10k preset manager
- [ ] Import and export custom themes

> Features marked complete are implemented in the current script, but still need testing across Termux versions and devices.

## Safety notes

- Review scripts before running them.
- Only install fonts from sources you trust.
- Use direct HTTPS links for remote downloads.
- Awesome Termux does not require root.
- The project modifies files inside the Termux home directory only.

## Credits

Termux · JetBrains Mono · Awesome Termux contributors

<div align="center">

**Awesome Termux**  
*Customize your terminal. Keep it awesome.*

</div>
