Canal+
======

[![Dernière version](https://img.shields.io/pypi/v/canalplus.svg?style=flat)](https://pypi.python.org/pypi/canalplus/)
[![Statut des tests](https://img.shields.io/travis/desbma/canalplus/master.svg?label=tests&style=flat)](https://travis-ci.org/desbma/canalplus)
[![Couverture](https://img.shields.io/coveralls/desbma/canalplus/master.svg?style=flat)](https://coveralls.io/github/desbma/canalplus?branch=master)
[![Version de Python supportées](https://img.shields.io/pypi/pyversions/canalplus.svg?style=flat)](https://pypi.python.org/pypi/canalplus/)
[![Licence](https://img.shields.io/github/license/desbma/canalplus.svg?style=flat)](https://pypi.python.org/pypi/canalplus/)

Canal+ est un script Python permettant de parcourir/visionner/télécharger les vidéos mises en ligne par la chaine Canal+ (Guignols de l'info, Groland, etc.).


## Fonctionnalités

* Permet de rechercher une vidéo
* Permet de télécharger/visionner toutes les vidéos d'un programme
* Permet de télécharger/visionner la dernière vidéo d'un programme
* Permet de visionner une vidéo dans un lecteur externe (MPV, VLC...)
* Fonctionne en mode interactif ou non
* Sélectionne automatiquement la meilleure qualité vidéo disponible
* Fonctionne en ligne de commande sur n'importe quel système (Linux, Mac, Windows, serveur sans interface graphique...)


## Installation

[Python](https://www.python.org/downloads/) >= 3.3 requis.

### A partir de PyPI (avec PIP)

1. Si pas déjà fait, [installer PIP](http://www.pip-installer.org/en/latest/installing.html) pour Python 3
2. Installer canalplus : `pip3 install canalplus`

### A partir des source

1. Si pas déjà fait, [installer setuptools](https://pypi.python.org/pypi/setuptools#installation-instructions) pour Python 3
2. Cloner ce dépot : `git clone https://github.com/desbma/canalplus`
3. Installer canalplus : `python3 setup.py install`


## Ligne de commande

Exécuter `canalplus -h` pour obtenir une liste complète des options disponibles.

Les vidéos téléchargées sont le plus souvent au format [MPEG-TS](https://fr.wikipedia.org/wiki/MPEG_Transport_Stream), lisible par [MPV](https://mpv.io/) ou [VLC](https://www.videolan.org/vlc/).

Si FFMpeg ou LibAV est detecté sur le système, les vidéos sont automatiquement "remuxées" au format [MP4](https://fr.wikipedia.org/wiki/MPEG-4_Part_14), plus couramment supporté.

Sous Windows, si vous rencontrez une erreur `UnicodeEncodeError`, pour certaines recherches uniquement, celà est du à un à un problème d'affichage des caractères à la console. [Pour régler ce problème, il suffit de définir la variable d'environnement `PYTHONIOENCODING` à `:ignore`](https://github.com/desbma/canalplus/issues/4#issuecomment-168416816).

### Exemples

* Lister toutes les vidéos des Guignols, et visionner la sélection avec VLC :

    `canalplus -p '?guignols' player:vlc`

* Télécharger la dernière vidéo de Groland dans `~/Bureau` :

    `canalplus -p '?groland' -m last ~/Bureau`

* Naviguer dans les programmes et vidéos interactivement, et visionner la sélection avec VLC :

    `canalplus player:vlc`

* Télécharger toutes les bandes annonces sur le bureau :

    `canalplus -p 'Dernieres Bandes Annonces' -m auto ~/Bureau`


## Licence

[GPLv3](https://www.gnu.org/licenses/gpl-3.0-standalone.html)
