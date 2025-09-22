- [What is this project](#what-is-this-project)
- [A apporter](#a-apporter)
- [Vérification support windows 11](#vérification-support-windows-11)
- [Vérification des problèmes connus](#vérification-des-problèmes-connus)
  - [Laptop](#laptop)
  - [Desktop](#desktop)
  - [Imprimantes / scanners](#imprimantes--scanners)
- [Vérification de la configuration matérielle](#vérification-de-la-configuration-matérielle)
  - [Windows](#windows)
  - [Linux](#linux)
  - [Autre](#autre)
  - [Vérifications](#vérifications)
- [Distribution](#distribution)
  - [Choix de la distribution](#choix-de-la-distribution)
  - [Télécharger la distribution](#télécharger-la-distribution)
    - [Linux mint](#linux-mint)
    - [Debian](#debian)
    - [Ubuntu](#ubuntu)
  - [Vérifier le téléchargement](#vérifier-le-téléchargement)
- [Clé usb](#clé-usb)
  - [Préparation de la clé USB](#préparation-de-la-clé-usb)
    - [Sur windows](#sur-windows)
      - [BalenaEtcher vs Rufus](#balenaetcher-vs-rufus)
      - [Rufus](#rufus)
      - [BalenaEtcher](#balenaetcher)
    - [Sur linux](#sur-linux)
  - [Vérifier le contenu de la clé usb](#vérifier-le-contenu-de-la-clé-usb)
  - [Vérification clé usb endommagée](#vérification-clé-usb-endommagée)
- [Booter sur la clé USB](#booter-sur-la-clé-usb)
- [Changer la langue et la disposition du clavier](#changer-la-langue-et-la-disposition-du-clavier)
- [Checklist de bon fonctionnement (en live USB)](#checklist-de-bon-fonctionnement-en-live-usb)
- [Post-install](#post-install)
  - [Tuning des miroirs (mint)](#tuning-des-miroirs-mint)
  - [Vérification des sources logicielles (ubuntu)](#vérification-des-sources-logicielles-ubuntu)
  - [Mises à jour](#mises-à-jour)
  - [Checklist de bon fonctionnement après install](#checklist-de-bon-fonctionnement-après-install)
  - [Installation logiciels supplémentaires](#installation-logiciels-supplémentaires)
  - [Import des données](#import-des-données)
  - [Configuration timeshift](#configuration-timeshift)
- [Plus d'infos](#plus-dinfos)
  - [Dépannage](#dépannage)
  - [Cheatsheet](#cheatsheet)
  - [Autres sources d'info sur les linux install party](#autres-sources-dinfo-sur-les-linux-install-party)

# What is this project

Instructions (in French) for helping organizing linux install parties. 

The audience is windows users, thus the linux mint distro.

# A apporter

- Supports
  - Quelques clés usb prêtes avec les distributions souhaitées
  - Une clé USB avec [hirensbootcd](https://www.hirensbootcd.org/download/) si besoin de debugger ou mettre à jour le BIOS (système Windows PE)
  - Uné clé USB avec [finnix](https://www.finnix.org/) ([cheatsheet](CHEATSHEET.md#finnix))
- Internet
  - Connexion WIFI avec un mot de passe pas trop long
  - Ou réseau 4G/5G + hotspot WIFI avec un téléphone
  - Idéalement une prise Ethernet en cas de souci de WIFI avec un poste (à défaut un équipement type répétiteur wifi avec une sortie ethernet)
- Documentation pour les participants
  - Fiches programmes linux
- Autres
  - Ecouteurs (pour diagnostiquer problèmes de son)
  - Ecran, clavier, souris, cable HDMI, cable VGA, hub USB
  - Disque dur externe
  - Multi-prise, rallonge
  

# Vérification support windows 11

Dans le doute, vérifier si le PC est compatible W11 : [pc health check](https://support.microsoft.com/fr-fr/windows/v%C3%A9rifier-si-un-appareil-r%C3%A9pond-%C3%A0-windows-11-configuration-requise-apr%C3%A8s-avoir-modifi%C3%A9-le-mat%C3%A9riel-de-l-appareil-f3bc0aeb-6884-41a1-ab57-88258df6812b)

# Vérification des problèmes connus

Vérifier si des problèmes sont connus sur ubuntu avec ce matériel

## Laptop

| Site                                                         | Notes                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Ordinateur portable testés sous Ubuntu (fr)](https://doc.ubuntu-fr.org/portable) | Liste assez conséquente avec des versions ubuntu plutôt récentes |
| [Portables certifiés par canonical](https://ubuntu.com/certified/laptops) | L'idéal est d'être dans cette liste mais il n'y a pas toutes les marques / tous les portables |
| [Hardware Support Wiki - laptops (en)](https://wiki.ubuntu.com/HardwareSupport/Machines/Laptops?action=show&redirect=HardwareSupportMachinesLaptops) | Liste assez conséquente mais avec des versions ubuntu anciennes (liste plus mise à jour) |
| [Laptop testing old reports](https://wiki.ubuntu.com/Testing/Laptop/OldReports) | Petite liste plus mise à jour                                |
|                                                              |                                                              |

## Desktop

| Site                                                         | Notes                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Tours certifiées par canonical](https://ubuntu.com/certified/desktops) | L'idéal est d'être dans cette liste mais il n'y a pas toutes les marques / toutes les tours |
| [Hardware Support Wiki - desktops (en)](https://wiki.ubuntu.com/HardwareSupportMachinesDesktops) | Liste moyenne avec des versions ubuntu anciennes (liste plus mise à jour) |

## Imprimantes / scanners

| Objet                | Site                                                         | Notes                                                        |
| -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Scanners             | [liste des scanners connus pour bien fonctionner avec SANE](http://www.sane-project.org/sane-mfgs.html#SCANNERS) |                                                              |
| Imprimantes/scanners | [Hardware Support Wiki](https://wiki.ubuntu.com/HardwareSupport/) | La liste n'est plus mise à jour et les tests ont été faits sur des versions ubuntu très anciennes, mais on peut y jeter un oeil (si ça marchait alors, ça devrait toujours marcher) |

Voir aussi: https://doc.ubuntu-fr.org/imprimante

# Vérification de la configuration matérielle

A faire avant de commencer pour le choix de la distribution.

## Windows

Télécharger *speccy* de piriform dans le store microsoft

## Linux

```
sudo apt-get install hardinfo
```

## Autre

Si pas d'OS disponible (mot de passe oublié ou autre souci) on peut utiliser finnix ça démarrera plus vite qu'un live linux mint: cf [cheatsheet](CHEATSHEET.MD#analyse-hardware)

## Vérifications

Noter les caractéristiques: 

- CPU
  - Nombre de coeurs
  - Cadence
  - Architecture. La trouver depuis la marque + recherche internet si besoin. Les plus répandues
    - AMD 64-bits, Intel 64-bits: x86_64
    - Intel i386, i586, i686: c'est x86 32-bits (très ancien)
- RAM
  - Taille
- GPU
  - Modèle

# Distribution

## Choix de la distribution

(c'est un choix de notre part de privilégier Linux mint, il y a bien sur plein d'autres choix valables qui ne sont pas listés ici)

- 64-bits architecture amd64 ou intel64:
  - cpu >= dual core 2GB et RAM >= 4GB: **Linux mint mate** (estimation, pas de source officielle pour chaque flavor) (1)
  - sinon: **Linux mint xfce**
- 32-bits architecture armhf ([avec l'architecture ARMv7 / VFPv3](https://www.debian.org/releases/stable/armhf/ch02s01.en.html)) : **Debian**
- 64-bits autres architectures : voir https://www.debian.org/releases/stable/
- 32-bits autres architectures: **pas de solution?**



(1) [requirements linux mint](https://linuxmint.com/faq.php#:~:text=2GB%20RAM%20(4GB%20recommended%20for,t%20fit%20in%20the%20screen).):

- 2GB RAM (4GB recommended for a comfortable usage).
- 20GB of disk space (100GB recommended).
- 1024×768 resolution (on lower resolutions, press ALT to drag windows with the mouse if they don’t fit in the screen).



Pour référence, [pré-requis Ubuntu 24.04](https://ubuntu.com/download/desktop): 2GHz dual core, 4GB RAM

##  Télécharger la distribution

### Linux mint

- Lien de téléchargement **Mate** ou **Xfce**: https://linuxmint.com/download.php

### Debian

Préférer la distribution full "DVD" pas la netinst "CD". La netinst nécessite de re-télécharger des paquets et ça ne fonctionne pas forcément sur WIFI. Attention la distribution full pèse plus de 4GB  (4.4GB en 13.0.0)

**Lien de téléchargement debian 32-bits armhf:** https://cdimage.debian.org/debian-cd/current/armhf/iso-dvd/

### Ubuntu

- [Download](https://ubuntu.com/download/desktop)

- [Checksum du fichier iso](https://releases.ubuntu.com/) (cliquer sur la bonne version, puis télécharger le fichier `SHA256SUMS`)

## Vérifier le téléchargement

Linux: 

```
sha256sum xxx.iso
```



Windows:

```
 certUtil -hashfile xxx.iso SHA256
```



# Clé usb

## Préparation de la clé USB

### Sur windows

#### BalenaEtcher vs Rufus

Utiliser Etcher ou Rufus:

- Etcher est plus simple d'usage (mais parfois moins stable?)
  - Ubuntu préconise etcher

- Rufus a plus d'options et est plus léger
  - Linux mint préconise Rufus


#### Rufus

https://rufus.ie/fr/

- Appuyer sur alt+E pour activer le mode dual UEFI/BIOS pour un maximum de compatibilité
- Schéma de partition
  - Préférer *MBR* pendant encore quelques années (compatible BIOS et UEFI)
  - Avancé / cocher "Ajouter les options de compatibilité pour vieux BIOS"
- Système de fichiers: FAT32
- Popup à la fin mode ISO vs DD
  - Pour mint: choisir ISO
  - Pour debian: choisir DD (troubleshooting plantage sur "chargement des composants depuis le support d'installation")
  - Pour ubuntu: choisir DD (ne boot pas sinon)


#### BalenaEtcher

https://etcher.balena.io/#download-etcher

### Sur linux

- Linux mint:
  - utiliser *Créateur de clé USB* (*USB image writer*) installé par défaut
- Debian, Ubuntu: 
  - balenas etcher. Utiliser le [fichier zip](https://etcher.balena.io/#download-etcher) qu'on décompresse pour utiliser sur place, pas le .deb (problèmes de dépendances)

## Vérifier le contenu de la clé usb

Si pas dejà fait (Etcher le fait)

```
md5sum -c mdsum.txt
```

(en cas d'erreur, un message apparait à la fin)

## Vérification clé usb endommagée

Dans le doute, on peut vérifier si la clé est endommagée. Prévoir 30mn environ pour une clé de 8GB

Vérifier la taille des blocks: 

```
blockdev --getbsz /dev/sdX
```

Ecrire des blocks aléatoires et vérifier le résultat:

```
badblocks -w -s -o error.log -b <block_size> -t random /dev/sdX
```



# Booter sur la clé USB

| Manufacturer       | Bios configuration | Boot Menu                       | Alternative Keys |
| ------------------ | ------------------ | ------------------------------- | ---------------- |
| Acer               | F2                 | F12                             | Del              |
| Asus               | F2                 | Esc                             | Del              |
| Dell               | F2                 | F12                             |                  |
| Gateway            | F2                 | F12                             |                  |
| Gigabyte           | Del                | F12                             | F2               |
| HP                 | Esc, F10           | F9                              |                  |
| Lenovo (Consumer)  | F2                 | F12                             | Fn + F2          |
| Lenovo (ThinkPads) | Enter, F1          | F12                             |                  |
| MSI                | Del                | F11                             |                  |
| Sony               | F2                 | Assist button (for VAIO models) |                  |
| Toshiba            | F2                 | F12                             | Esc              |
| Samsung            | F2                 | Esc                             | F12              |
| Fujitsu            | F2                 | F12                             |                  |
| Intel NUC          | F2                 | F10                             |                  |

[Ref](https://pendrivelinux.com/how-to-access-bios/)

# Changer la langue et la disposition du clavier

cf [cheatsheet](CHEATSHEET.md#langues)

# Checklist de bon fonctionnement (en live USB)

- Touchpad
- Accès internet en WIFI
- Accès internet en ethernet (si possible)
- Accéder à un site internet en https (ex `https://google.com`)
- Carte son: jouer une vidéo sur youtube
- GPU:
  - Vérifier que la carte graphique apparait dans hardinfo (installer hardinfo)
  - Faire bouger rapidement une fenêtre.
  - Dans le doute faire un test avec [furmark](https://www.materiel.net/guide-achat/g8-les-cartes-graphiques/10006/)
- Mise en veille: mettre l'ordinateur en veille. S'assurer que le disque dur ne tourne plus / que le système n'est plus sous tension (au bruit). Sortir l'ordinateur de la veille.
- Brancher un moniteur externe HDMI ou VGA (si besoin)
- Bluetooth (si besoin)
- Lecteur de carte SD (si besoin)

# Post-install

## Tuning des miroirs (mint)

- Menu / Sources de logiciels
  - Principal et base: pointer sur des miroirs plus proches géographiquement

## Vérification des sources logicielles (ubuntu)

Vérifier que les sources de logiciels sont bien toutes cochées : 

- Menu / Logiciels et mises à jour / Logiciels ubuntu
  - Logiciel libre et open source maintenu par Canonical (main)
  - Logiciel libre et open source maintenu par la communauté (universe)
  - Pilotes propriétaires de périphériques (restricted)
  - Logiciels restreintes par des droits d'auteur ou des questions juridiques (multiverse)

et choisir : télécharger depuis : Serveur pour France

## Mises à jour

Mettre à jour et rebooter.

## Checklist de bon fonctionnement après install

Refaire une passe rapide sur les vérifications déjà faite en live USB

## Installation logiciels supplémentaires

- Si besoin d'utiliser un scanner: xsane
- [Teamviewer quicksupport](https://www.teamviewer.com/fr/download/linux/)

## Import des données

cf [import des données](IMPORT_DONNEES.md)

## Configuration timeshift

Configurer timeshift: 

- mensuel, garder 2

# Plus d'infos

## Dépannage

cf [Dépannage](TROUBLESHOOTING.md)

## Cheatsheet

cf [Cheatsheet](CHEATSHEET.md)

## Autres sources d'info sur les linux install party

Voir aussi [cette page](https://docs.lacontrevoie.fr/activites/ateliers/install-party/) qui est très bien faite
