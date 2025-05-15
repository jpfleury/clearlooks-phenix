## À propos

![Clearlooks-Phénix](https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/poster.jpg)

Le projet Clearlooks-Phénix a pour but de créer une version GTK 3 de Clearlooks, thème par défaut de GNOME 2. Un style est également inclus pour GTK 2, Unity et les gestionnaires de fenêtres Metacity, Openbox et Xfwm4.

*À noter que GTK était auparavant connu sous le nom de GTK+.*

### Captures d'écran

Voici quelques captures d'écran (s'il y a lieu, cliquer pour voir l'image au format original):

<a href="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple1.png"><img src="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple1.png" alt="Capture d'écran du bureau sous GNOME 3 (mode fallback) avec le thème Clearlooks-Phénix" width="659" height="494"></a>

<a href="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/gimp.png"><img src="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/gimp.png" alt="Capture d'écran de GIMP avec le thème Clearlooks-Phénix" width="659" height="358"></a>

<img src="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple2.png" alt="Capture d'écran de gedit 3 avec le thème Clearlooks-Phénix" width="659" height="537">

<a href="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple3.png"><img src="https://raw.githubusercontent.com/jpfleury/clearlooks-phenix/master/doc/exemple3.png" alt="Capture d'écran de GTK+ Widget Factory avec le thème Clearlooks-Phénix" width="659" height="444"></a>

## Dépendances

- Dépendances de Clearlooks-Phénix v1: paquet `gnome-themes-standard`.

- Dépendances de Clearlooks-Phénix v2: paquets `gnome-themes-standard` et `gtk3-engines-unico`.

Dans tous les cas, il faut installer le paquet `gtk2-engines` si des logiciels GTK 2 sont utilisés.

## Installation

- Télécharger l'archive de la version correspondant à votre situation:

	- pour GTK 3.0/3.2: [télécharger Clearlooks-Phénix v1](https://github.com/jpfleury/clearlooks-phenix/archive/v1.zip);
	
	- pour GTK 3.4: [télécharger Clearlooks-Phénix v2](https://github.com/jpfleury/clearlooks-phenix/archive/v2.zip);
	
	- pour GTK 3.6: [télécharger Clearlooks-Phénix v3](https://github.com/jpfleury/clearlooks-phenix/archive/v3.zip);
	
	- pour GTK 3.8: [télécharger Clearlooks-Phénix v4](https://github.com/jpfleury/clearlooks-phenix/archive/v4.zip);
	
	- pour GTK 3.10/3.12: [télécharger Clearlooks-Phénix v5](https://github.com/jpfleury/clearlooks-phenix/archive/v5.zip);
	
	- pour GTK 3.14/3.18: [télécharger Clearlooks-Phénix v6](https://github.com/jpfleury/clearlooks-phenix/archive/v6.zip);
	
	- pour GTK 3.20+: [télécharger Clearlooks-Phénix v7](https://github.com/jpfleury/clearlooks-phenix/archive/master.zip).
	
	Pour vérifier votre version de GTK, exécutez `gtk-launch --version` dans un terminal.

- Extraire l'archive.

- Renommer le dossier extrait en `Clearlooks-Phenix`.

- Copier le dossier `Clearlooks-Phenix` dans un des deux emplacements suivants:

	- `~/.themes/` pour l'utilisateur courant;
	
	- `/usr/share/themes/` pour tous les utilisateurs, incluant le style des logiciels lancés en tant que superutilisateur (par exemple Synaptic).

### Sélection du thème

Le thème doit être sélectionné une fois l'installation terminée:

- Sous GNOME: avec le logiciel [gnome-tweak-tool](https://live.gnome.org/GnomeTweakTool), en paramétrant *Theme > Window theme* et *Theme > GTK+ theme*, ou en console:

		dconf write /org/gnome/desktop/wm/preferences/theme \'Clearlooks-Phenix\'
		dconf write /org/gnome/desktop/interface/gtk-theme \'Clearlooks-Phenix\'

- Sous Xfce: en allant dans *Paramètres > Apparence > Style* du menu principal pour le thème GTK, et dans *Paramètres > Gestionnaire de fenêtres > Style* pour le thème de Xfwm4, ou en console:

		xfconf-query -s Clearlooks-Phenix -c xfwm4 -p /general/theme
		xfconf-query -s Clearlooks-Phenix -c xsettings -p /Net/ThemeName

- Sinon, définissez `gtk-theme-name` dans `$XDG_CONFIG_HOME/settings.ini` (GTK 3) ou dans `~/.gtkrc-2.0` (GTK 2).

## Configuration

### Bureau géré par Nautilus

Par défaut, le texte des icônes sur un bureau géré par Nautilus est noir. Pour afficher le texte en blanc, ouvrir le fichier `gtk-3.0/applications.css` dans un éditeur de texte, trouver le code relatif à Nautilus:

	/************
	 * Nautilus *
	 ************/
	
	/*
	CODE
	CSS
	COMMENTÉ
	*/

et le décommenter, ce qui donne:

	/************
	 * Nautilus *
	 ************/
	
	CODE
	CSS
	DÉCOMMENTÉ

Pour avoir une couleur personnalisée, modifier la couleur directement dans le fichier `gtk-3.0/applications.css`.

### Emplacement des boutons de fenêtres

Si après une installation ou une mise à jour d'Ubuntu, les boutons de fenêtres se trouvent à gauche, mais que vous les voulez à droite, lancez la commande suivante dans une console:

	gconftool-2 --set /apps/metacity/general/button_layout --type string ":minimize,maximize,close"

### Arrière-plan

L'arrière-plan utilisé dans la capture d'écran du bureau de GNOME est disponible dans le dossier `wallpapers`.

### Icônes

Le thème d'icônes utilisé dans la même capture d'écran est Mist, installé avec le paquet `gnome-themes`, sous licence LGPL. Cependant, ce paquet n'est plus disponible. Voici une méthode simple pour installer Mist:

- [Télécharger l'archive de la dernière version disponible du paquet `gnome-themes`.](https://snapshot.debian.org/archive/debian-ports/20091029T000000Z/pool/main/g/gnome-themes/gnome-themes_2.28.1-1_all.deb)

- Extraire l'archive.

- Copier le dossier `usr/share/icons/Mist` dans un des deux emplacements suivants:

	- `~/.icons/` pour l'utilisateur courant;
	
	- `/usr/share/icons/` pour tous les utilisateurs.

- Ensuite, choisir le thème d'icônes Mist:

	- sous GNOME: avec le logiciel gnome-tweak-tool en paramétrant *Theme > Icon theme*;
	
	- sous Xfce: en allant dans *Paramètres > Apparence > Icônes* du menu principal.

## Développement et licence

Le logiciel Git est utilisé pour la gestion de versions. [Le dépôt peut être consulté en ligne ou récupéré en local.](https://github.com/jpfleury/clearlooks-phenix)

Merci à Yuri Khan pour l'affichage HiDPI, ainsi qu'à Andrew Shadura, Andrey Cherepanov, jsane-h8ms et d'autres pour leurs contributions au support de GTK 3.20+.

Auteur: Jean-Philippe Fleury (<https://github.com/jpfleury>)  
Copyright © Jean-Philippe Fleury, 2011-2014, 2025.  
Copyright © Andrew Shadura, 2013-2014.

Ce programme est un logiciel libre; vous pouvez le redistribuer ou le
modifier suivant les termes de la GNU General Public License telle que
publiée par la Free Software Foundation: soit la version 3 de cette
licence, soit (à votre gré) toute version ultérieure.

Ce programme est distribué dans l'espoir qu'il vous sera utile, mais SANS
AUCUNE GARANTIE: sans même la garantie implicite de COMMERCIALISABILITÉ
ni d'ADÉQUATION À UN OBJECTIF PARTICULIER. Consultez la Licence publique
générale GNU pour plus de détails.

Vous devriez avoir reçu une copie de la Licence publique générale GNU avec
ce programme; si ce n'est pas le cas, consultez
<http://www.gnu.org/licenses/>.

### Matériel tiers

- Thème Adwaita, provenant du paquet [`gnome-themes-standard`](http://packages.ubuntu.com/search?keywords=gnome-themes-standard), sous licence LGPL.

- Fichier `gtk-2.0/gtkrc`, provenant du paquet [`gtk2-engines`](http://packages.ubuntu.com/search?keywords=gtk2-engines), sous licence LGPL.

- Fichier `metacity-1/metacity-theme-1.xml`, provenant du paquet [`gnome-themes-selected`](http://packages.ubuntu.com/search?keywords=gnome-themes-selected), sous licence LGPL.

- Fichier `openbox-3/themerc`, provenant du paquet [`openbox`](http://packages.ubuntu.com/search?keywords=openbox), sous licence GPL.

- Thème [Clearlooks XFWM4](http://xfce-look.org/content/show.php/Clearlooks+for+XFWM4?content=137055), sous licence GPL.

- Fichiers dans `wallpapers`, basés sur une [image de volvoguy](http://gnome-look.org/content/show.php?content=22210), sous licence GPL.
