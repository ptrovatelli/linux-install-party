- [What is this project](#what-is-this-project)
- [A apporter](#a-apporter)
- [Vérification des problèmes connus](#vérification-des-problèmes-connus)
- [Vérification de la configuration matérielle](#vérification-de-la-configuration-matérielle)
  - [Windows](#windows)
  - [Linux](#linux)
  - [Vérifications](#vérifications)
- [Distribution](#distribution)
  - [Choix de la distribution](#choix-de-la-distribution)
  - [Télécharger la distribution](#télécharger-la-distribution)
    - [Linux mint](#linux-mint)
    - [Debian](#debian)
- [Préparation de la clé USB](#préparation-de-la-clé-usb)
  - [BalenaEtcher vs Rufus](#balenaetcher-vs-rufus)
  - [Rufus](#rufus)
  - [BalenaEtcher](#balenaetcher)
- [Booter sur la clé USB](#booter-sur-la-clé-usb)
- [Checklist de bon fonctionnement (en live USB)](#checklist-de-bon-fonctionnement-en-live-usb)
- [Checklist de bon fonctionnement (après install)](#checklist-de-bon-fonctionnement-après-install)
- [Post-install](#post-install)
  - [Tuning des miroirs (mint)](#tuning-des-miroirs-mint)
  - [Vérification des sources logicielles (ubuntu)](#vérification-des-sources-logicielles-ubuntu)
  - [Mises à jour](#mises-à-jour)
  - [Installation logiciels supplémentaires](#installation-logiciels-supplémentaires)
  - [Import des données](#import-des-données)
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
  

# Vérification des problèmes connus

Vérifier si des problèmes sont connus sur ubuntu avec ce matériel:

- [Ordinateur portable testés sous Ubuntu (fr)](https://doc.ubuntu-fr.org/portable)
- [Hardware Support Wiki - desktops (en)](https://wiki.ubuntu.com/HardwareSupportMachinesDesktops)
- [Hardware Support Wiki - laptops (en)](https://wiki.ubuntu.com/HardwareSupport/Machines/Laptops?action=show&redirect=HardwareSupportMachinesLaptops)

# Vérification de la configuration matérielle

A faire avant de commencer pour le choix de la distribution.

## Windows

Télécharger *speccy* de piriform dans le store microsoft

## Linux

```
sudo apt-get install hardinfo
```

## Vérifications

Noter les caractéristiques: 

- CPU
  - Nombre de coeurs
  - Cadence
  - Architecture. La trouver depuis la marque + recherche internet si besoin. Les plus répandues
    - AMD 64-bits, Intel 64-bits: x86_64 (support 64 bits à vérifier)
    - Intel i386, i586, i686: c'est x86 32-bits (très ancien)
- RAM
  - Taille
- GPU
  - Modèle

# Distribution

## Choix de la distribution

- 64-bits architecture amd64 ou intel64:
  - cpu >= dual core 1.6GB et RAM >= 4GB: **Linux mint mate** (estimation, pas de source officielle?)
  - sinon: **Linux mint xfce**
- 32-bits architecture armhf ([avec l'architecture ARMv7 / VFPv3](https://www.debian.org/releases/stable/armhf/ch02s01.en.html)) : **Debian**

- 64-bits autres architectures : voir https://www.debian.org/releases/stable/
- 32-bits autres architectures: **pas de solution?**

##  Télécharger la distribution

### Linux mint

- Lien de téléchargement **Mate**: https://linuxmint.com/edition.php?id=321
- Lien de téléchargement **Xfce**: https://linuxmint.com/edition.php?id=320

### Debian

Préférer la distribution full "DVD" pas la netinst "CD". La netinst nécessite de re-télécharger des paquets et ça ne fonctionne pas forcément sur WIFI. Attention la distribution full pèse plus de 4GB  (4.4GB en 13.0.0)

**Lien de téléchargement debian 32-bits armhf:** https://cdimage.debian.org/debian-cd/current/armhf/iso-dvd/

# Préparation de la clé USB

## BalenaEtcher vs Rufus

Utiliser Etcher ou Rufus:

- Etcher est plus simple d'usage (mais parfois moins stable?)

- Rufus a plus d'options et est plus léger

## Rufus

https://rufus.ie/fr/

- Appuyer sur alt+E pour activer le mode dual UEFI/BIOS pour un maximum de compatibilité
- Schéma de partition
  - Préférer *MBR* pendant encore quelques années (compatible BIOS et UEFI)
- Système de fichiers: FAT32
- Popup à la fin mode ISO vs DD : choisir ISO (?)

## BalenaEtcher

https://etcher.balena.io/#download-etcher

# Booter sur la clé USB

- Bios hotkey: paramètres BIOS complets
- Boot menu key: juste pour sélectionner un media de démarrage une fois

| Manufacturer       | BIOS Hotkey | Boot Menu Key                   | Alternative Keys |
| ------------------ | ----------- | ------------------------------- | ---------------- |
| Acer               | F2          | F12                             | Del              |
| Asus               | F2          | Esc                             | Del              |
| Dell               | F2          | F12                             |                  |
| Gateway            | F2          | F12                             |                  |
| Gigabyte           | Del         | F12                             | F2               |
| HP                 | Esc, F10    | F9                              |                  |
| Lenovo (Consumer)  | F2          | F12                             | Fn + F2          |
| Lenovo (ThinkPads) | Enter, F1   | F12                             |                  |
| MSI                | Del         | F11                             |                  |
| Sony               | F2          | Assist button (for VAIO models) |                  |
| Toshiba            | F2          | F12                             | Esc              |
| Samsung            | F2          | Esc                             | F12              |
| Fujitsu            | F2          | F12                             |                  |
| Intel NUC          | F2          | F10                             |                  |

[Ref](https://pendrivelinux.com/how-to-access-bios/)

# Checklist de bon fonctionnement (en live USB)

- Imprimante/scanner: vérifier qu'il existe des drivers pour linux sur la base de la marque/modèle [et si des problèmes sont connus](https://wiki.ubuntu.com/HardwareSupport/)
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
- Bluetooth (si besoin)
- Lecteur de carte SD (si besoin)

# Checklist de bon fonctionnement (après install)

Refaire une passe rapide sur les vérifications déjà faite en live USB

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

## Installation logiciels supplémentaires

TODO

## Import des données

cf [import des données](IMPORT_DONNES.md)

# Plus d'infos

## Dépannage

cf [Dépannage](TROUBLESHOOTING.md)

## Cheatsheet

cf [Cheatsheet](CHEATSHEET.md)

## Autres sources d'info sur les linux install party

Voir aussi [cette page](https://docs.lacontrevoie.fr/activites/ateliers/install-party/) qui est très bien faite
