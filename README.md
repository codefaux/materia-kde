<img src="https://raw.githubusercontent.com/codefaux/materia-kde/master/logo.png" alt="materia-kde-logo" align="right" />

# Materia KDE

This is a hack of a port of the seemingly-abandoned [GTK theme Materia](https://github.com/nana-4/materia-theme) for the Plasma 5, to make it work on Plasma 6 a desktop with a few additions and extras.

I (@codefaux) do not use Gnome or KDE, but I got really tired of which theme I saw on what app being a dice roll, so I'm making them work ENOUGH FOR MY USES for a consistent experience. I also have a [fork of materia-theme](https://github.com/codefaux/materia-theme) in case I need to fix it. Feel free to use it. I'm sorry if they don't work for yours; let me know and I'll try to help if/where I can.

Original instructions below, pruned to avoid references to the original.

In this repository you'll find:
- Aurorae window decoration themes
- Konsole color schemes
- Kvantum themes
- Plasma color schemes
- Plasma Desktop themes
- Plasma Look-and-Feel settings
- Yakuake skins
- SDDM themes
- Wallpapers

## Installation

### Materia KDE installer

#### Install

Use this command to install the latest version directly from this repo (independently of your distro's package manager, which makes assumptions and maybe isn't a great idea):

```
wget -qO- https://raw.githubusercontent.com/codefaux/materia-kde/master/install.sh | sh
```

#### Uninstall

```
wget -qO- https://raw.githubusercontent.com/codefaux/materia-kde/master/install.sh | uninstall=true sh
```

### Third-party packages

- I won't be explicitly maintaining any distribution's packages. Let me know if you know how or need me to build one, especially if it can be done using Github workflows. I'm not interested in maintaining packages, but if they can be automated I certainly won't object.

**NOTE:** If you are a maintainer and want your package to be in this list, please feel free to create an issue or pull request.

### Everything below is from the original repo, these are not @codefaux responsibility

## Recommendations

- For a more consistent look on Qt and KDE apps, please use this theme with the [Kvantum engine](https://github.com/tsujan/Kvantum). \
  Run `kvantummanager`, then choose and apply the **Materia** theme.
- Install [Papirus icon theme](https://github.com/PapirusDevelopmentTeam/papirus-icon-theme) for a more consistent and beautiful experience.
- Install and use these widgets: [Minimal Menu](https://www.opendesktop.org/p/1275285/) and [Digital Clock WL](https://www.opendesktop.org/p/1311422/)
- Change the System Settings view to **Icons View**
- Set the icon size for Toolbar and Main Toolbar to **16px**
- Set the border size to **No Borders** in Window Decoration settings

### Hacks for smaller screen resolutions

- Install the [Active Window Control](https://www.opendesktop.org/p/998910/) and [Application Menu](https://cgit.kde.org/plasma-workspace.git/tree/applets/appmenu) widgets, and move them to a panel. \
  (**NOTE:** Application Menu is already included with recent versions of KDE Plasma, so there is no need to install it manually.)
- Disable window buttons and titlebar on window decorations:
  - Open the theme's rc file (**Materiarc**, **Materia-Darkrc**, or **Materia-Lightrc**) on the Aurorae themes folder (this is usually located in **~/.local/share/aurorae/themes** or **/usr/share/aurorae/themes**) and change the following lines:
    ```
    ButtonHeight=0
    ButtonWidth=0
    TitleHeight=0
    TitleEdgeTop=0
    ```
  - To hide window buttons on GTK 3 apps, use the [GTK3-noCSD](https://github.com/PCMan/gtk3-nocsd) script

## Known issues

### Aurorae rendering bugs with NVIDIA graphics

On systems using the proprietary NVIDIA video driver, Aurorae window decorations [do not render properly](https://bugs.kde.org/show_bug.cgi?id=384457) by default with all themes.

| **Wrong rendering** | **Correct rendering** |
|:--------------------|:----------------------|
| ![wrong-rendering](https://i.imgur.com/rS5OgPf.png) | ![right-rendering](https://i.imgur.com/5OKjULE.png) |

To fix that, use this config on **~/.Xresources**:
```
Xft.dpi:       96
Xft.antialias: true
Xft.hinting:   true
Xft.autohint:  false
Xft.hintstyle: hintslight
Xft.lcdfilter: lcddefault
Xft.rgba:      rgb
```
Restart your PC to apply these changes.

### Inconsistent styles in QML/Kirigami apps

Recent Qt and KDE apps now use QML or Kirigami — these do *NOT* fully support theming on *any* engine because more elements are *hardcoded*. Please do not submit new issues regarding such apps; we can't do anything to fix them.

Affects apps include, but are not limited to:
- Muon Discover
- Kirigami Gallery
- Ikona
- Alligator
- Kaidan
- Elisa
- KDE Itinerary
- KTrip
- Kirogi
- VVave (ex Babe)
- Keysmith
- Calindori
- KDE Connect SMS Module
- Some `systemsettings5` and `kcm` modules
- and more...

## License

Copyright © 2018–2021 [Alexey Varfolomeev](https://github.com/varlesh) and contributors.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
