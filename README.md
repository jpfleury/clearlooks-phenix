## Overview

The Clearlooks-Phénix project aims at creating a GTK3 port of Clearlooks, the default theme for Gnome 2. Style is also included for GTK2, Unity and for Metacity, Openbox and Xfwm4 window managers.

Here are screenshots (if applicable, click to see the original image):

<a href="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple1.png"><img src="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple1.png" alt="Screenshot of a Gnome 3 desktop (fallback mode) with the Clearlooks-Phénix theme" width="658" height="493" /></a>

<img src="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple2.png" alt="Screenshot of gedit 3 with the Clearlooks-Phénix theme" width="659" height="537" />

<a href="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple3.png"><img src="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple3.png" alt="Screenshot of GTK+ Widget Factory with the Clearlooks-Phénix theme" width="658" height="435" /></a>

## Requirements

- Requirements for Clearlooks-Phénix v1: packages `gtk2-engines` (if GTK2 applications are used) and `gnome-themes-standard`.

- Requirements for Clearlooks-Phénix v2: packages `gtk2-engines` (if GTK2 applications are used), `gnome-themes-standard` and `gtk3-engines-unico`.

- Requirements for Clearlooks-Phénix v3 and newer: package `gtk2-engines` (if GTK2 applications are used).

## Installation

- Download the appropriate version according to your situation:

	- for GTK 3.0 and 3.2: [download Clearlooks-Phénix v1](https://github.com/jpfleury/clearlooks-phenix/archive/v1.zip);
	
	- for GTK 3.4: [download Clearlooks-Phénix v2](https://github.com/jpfleury/clearlooks-phenix/archive/v2.zip);
	
	- for GTK 3.6: [download Clearlooks-Phénix v3](https://github.com/jpfleury/clearlooks-phenix/archive/v3.zip);
	
	- for GTK 3.8: [download Clearlooks-Phénix v4](https://github.com/jpfleury/clearlooks-phenix/archive/v4.zip);
	
	- for GTK 3.10 and 3.12: [download Clearlooks-Phénix v5](https://github.com/jpfleury/clearlooks-phenix/archive/v5.zip);
	
	- for GTK 3.14: [download Clearlooks-Phénix v6](https://github.com/jpfleury/clearlooks-phenix/archive/v6.zip);
	
	- for GTK 3.20: [download Clearlooks-Phénix v7](https://github.com/jpfleury/clearlooks-phenix/archive/master.zip).
	
	To find your GTK version:
	
	- You can check in your package manager the version of the package `libgtk-3-0`.
	
	- If you use Ubuntu, here's a correspondence between its versions and those of GTK (for a default installation of Ubuntu):
	
		- Ubuntu 11.10: GTK 3.2
		- Ubuntu 12.04: GTK 3.4
		- Ubuntu 12.10 and 13.04: GTK 3.6
		- Ubuntu 13.10: GTK 3.8
		- Ubuntu 14.04: GTK 3.10
		- Ubuntu 14.10: GTK 3.12
		- Ubuntu 15.04: GTK 3.14
		- Ubuntu 15.10: GTK 3.16
		- Ubuntu 16.04: GTK 3.18
		- Ubuntu 16.10: GTK 3.20

- Extract the archive.

- Rename the extracted folder to `Clearlooks-Phenix`.

- Copy the folder `Clearlooks-Phenix` in one of the following two locations:

	- `~/.themes/` for the current user;
	
	- `/usr/share/themes/` for all users, including style for programs ran with root privileges (e.g. Synaptic).

### Selection

The theme must be selected once the installation is complete:

- On Gnome: with [gnome-tweak-tool](https://live.gnome.org/GnomeTweakTool), by setting *Theme > Window theme* and *Theme > GTK+ theme*, or in a terminal:

		dconf write /org/gnome/desktop/wm/preferences/theme \'Clearlooks-Phenix\'
		dconf write /org/gnome/desktop/interface/gtk-theme \'Clearlooks-Phenix\'

- On Xfce: by going to *Settings > Appearence > Style* in the main menu for the GTK theme, and to *Settings > Window Manager > Style* for the Xfwm4 theme, or in a terminal:

		xfconf-query -s Clearlooks-Phenix -c xfwm4 -p /general/theme
		xfconf-query -s Clearlooks-Phenix -c xsettings -p /Net/ThemeName

## Configuration

### Desktop managed by Nautilus

By default, the font color on a desktop managed by Nautilus is black. To set it to white, open the file `gtk-3.0/applications.css` with a text editor, find the code relative to Nautilus:

	/************
	 * Nautilus *
	 ************/
	
	/*
	COMMENTED
	CSS
	CODE
	*/

and uncomment it, as follows:

	/************
	 * Nautilus *
	 ************/
	
	UNCOMMENTED
	CSS
	CODE

To get a custom color, change the color directly in the file `gtk-3.0/applications.css`.

### Window buttons layout

If after installing or updating Ubuntu, the window buttons are on the left side, but you want them to the right, run the following command in a terminal:

	gconftool-2 --set /apps/metacity/general/button_layout --type string ":minimize,maximize,close"

### Wallpaper

The wallpaper used for the Gnome 3 desktop screenshot is available in the folder `wallpapers`.

### Icons

The icon theme used for the same screenshot is Mist, installed with the package `gnome-themes`, under LGPL. However, this package is no longer available with last Ubuntu versions. Here's an easy way to install Mist:

- [Download the archive of the Mist icon theme.](http://mirror.centos.org/centos/6/os/i386/Packages/gnome-themes-2.28.1-6.el6.noarch.rpm)

- Extract the archive.

- Copy the folder `usr/share/icons/Mist` in one of the following two locations:

	- `~/.icons/` for the current user;
	
	- `/usr/share/icons/` for all users.

- Then, choose Mist:

	- on Gnome: with gnome-tweak-tool by setting *Theme > Icon theme*;
	
	- on Xfce: by going to *Settings > Appearence > Icons* in the main menu.

## Development and license

Git is used for revision control. [Repository can be browsed online or cloned.](https://github.com/jpfleury/clearlooks-phenix)

Thanks to Andrew Shadura and Andrey Cherepanov for the support of GTK 3.20, and to Yuri Khan for the support of HiDPI.

Author: Jean-Philippe Fleury (<http://www.jpfleury.net/en/contact.php>)  
Copyright © 2011-2014 Jean-Philippe Fleury  
Copyright © 2013-2014 Andrew Shadura

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

### Third-party code

- Adwaita theme, from the package [`gnome-themes-standard`](http://packages.ubuntu.com/search?keywords=gnome-themes-standard), under LGPL.

- File `gtk-2.0/gtkrc`, from the package [`gtk2-engines`](http://packages.ubuntu.com/search?keywords=gtk2-engines), under LGPL.

- File `metacity-1/metacity-theme-1.xml`, from the package [`gnome-themes-selected`](http://packages.ubuntu.com/search?keywords=gnome-themes-selected), under LGPL.

- File `openbox-3/themerc`, from the package [`openbox`](http://packages.ubuntu.com/search?keywords=openbox), under GPL.

- [Clearlooks XFWM4](http://xfce-look.org/content/show.php/Clearlooks+for+XFWM4?content=137055) theme, under GPL.

- Files in `wallpapers`, based on an [image from volvoguy](http://gnome-look.org/content/show.php?content=22210), under GPL.
