[[_TOC_]]

# What is this project

Instructions (in French) for helping organizing linux install parties

# A apporter

- Supports
  - Quelques clé usb prêtes avec les distributions souhaitées
  - Une clé USB avec [hirensbootcd](https://www.hirensbootcd.org/download/) si besoin de debugger ou mettre à jour le BIOS
  - Uné clé USB avec [finnix](https://www.finnix.org/)
    - [Exemples d'utilisation](https://cp.vcclhosting.com/index.php?rp=%2Fknowledgebase%2F15%2FUsing-Finnix-Rescue-CD-to-Rescue-Repair-or-Backup-Your-Linux-System.html&&systpl=hexa)
- Internet
  - Connexion WIFI avec un mot de passe pas trop long
  - Ou réseau 4G/5G + hotspot WIFI avec un téléphone
  - Idéalement une prise Ethernet en cas de souci de WIFI avec un poste (à défaut un équipement type répétiteur wifi avec une sortie ethernet)
- Documentation pour les participants
  - Fiches programmes linux

# Vérification de la configuration matérielle

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
- 32-bits architecture armhf : **Debian**
  - Voir aussi les pré-requis: https://www.debian.org/releases/stable/armhf/ch02s01.en.html
    - *Debian/armhf works only on newer 32-bit ARM processors which implement at least the ARMv7 architecture with version 3 of the ARM vector floating point specification (VFPv3).*

- 64-bits autre architecture : voir https://www.debian.org/releases/stable/
- 32-bits autre architecture: **pas de solution?**

##  Télécharger la distribution

## Linux mint

- Lien de téléchargement **Mate**: https://linuxmint.com/edition.php?id=321
- Lien de téléchargement **Xfce**: https://linuxmint.com/edition.php?id=320

## Debian

Préférer la distribution full "DVD" pas la netinst "CD". La netinst nécessite de re-télécharger des paquets et ça ne fonctionne pas forcément sur WIFI! Attention la distribution full pèse plus de 4GB  (4.4GB en 13.0.0)

**Lien de téléchargement debian 32-bits armhf:** https://cdimage.debian.org/debian-cd/current/armhf/iso-dvd/

# Préparation de la clé USB

## BalenaEtcher vs Rufus

Utiliser Etcher ou Rufus:

- Etcher est plus simple d'usage

- Rufus a plus d'options et est plus léger

## BalenaEtcher

https://etcher.balena.io/#download-etcher

## Rufus

https://rufus.ie/fr/

- Appuyer sur alt+E pour activer le mode dual UEFI/BIOS pour un maximum de compatibilité
- Schéma de partition
  - Préférer *MBR* pendant encore quelques années (compatible BIOS et UEFI)
- Système de fichiers: FAT32
- Popup à la fin mode ISO vs DD : choisir ISO (?)

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

# Checklist de bon fonctionnement

- Imprimante/scanner: vérifier qu'il existe des drivers pour linux sur la base de la marque/modèle
- Touchpad
- Accès internet en WIFI
- Accès internet en ethernet (si possible)
- Accéder à un site internet en https (ex `https://google.com`)
- Carte son: jouer une vidéo sur youtube
- GPU:
  - Vérifier que la carte graphique apparait dans hardinfo
  - Faire bouger rapidement une fenêtre.
  - Dans le doute faire un test avec [furmark](https://www.materiel.net/guide-achat/g8-les-cartes-graphiques/10006/)
- Mise en veille: mettre l'ordinateur en veille. S'assurer que le disque dur ne tourne plus (au bruit). Sortir l'ordinateur de la veille.
- Vérification que les sources de logiciels sont bien tous cochés
- Bluetooth (si besoin)
- Lecteur de carte SD (si besoin)

# Dépannage

## Tiret blanc qui clignote / ne boot pas

Au moment de booter sur la clé, rien ne s'affiche à part un tiret blanc qui clignote. Ca indique un plantage très tôt dans le lancement. Peut-être une incompatibilité d'architecture de CPU avec la distribution de la clé usb

Autres pistes: 

- Assurez-vous que le BIOS est en UEFI si disponible (pas en Legacy)
- Désactiver le Secure Boot, désactiver les « Windows Optimized Defaults » ou d’autres options similaires.

# Plus d'infos

Voir aussi [cette page](https://docs.lacontrevoie.fr/activites/ateliers/install-party/) qui est très bien faite
