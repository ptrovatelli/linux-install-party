# Problèmes connus

Voir si des problèmes sont connus avec le matériel qui dysfonctionne: [hardware support wiki](https://wiki.ubuntu.com/HardwareSupport/)

# Boot

## Tiret blanc qui clignote / ne boot pas

Au moment de booter sur la clé, rien ne s'affiche à part un tiret blanc qui clignote (ou pas). Ca indique un plantage très tôt dans le lancement. Peut-être une incompatibilité d'architecture du CPU avec la distribution de la clé usb

Autres pistes: 

- Assurez-vous que le BIOS est en UEFI si disponible (pas en Legacy)
- Si UEFI n'est pas disponible pour cette machine, assurez-vous que le disque est bien partitionné en MBR avec [finnix](CHEATSHEET.md#finnix)

- Désactiver le Secure Boot, désactiver les « Windows Optimized Defaults » ou d’autres options similaires.

# Problèmes durant l'installation

## Debian n'arrive pas à charger les fichiers depuis le média d'installation

La clé USB faite avec rufus boot bien et lance l'installation, mais lorsqu'il faut récupérer les fichiers sur la clé ça ne fonctionne pas sur l'étape "chargement des composants depuis le support d'installation"

Solution: faire la clé en mode "dd" avec rufus au lieu de "iso" (popup après les options de configuration)



# Son

## Pas de son

- Ouvrir alsamixer et essayer différents canaux

- Essayer avec des écouteurs (souci carte son vs souci hauts-parleurs)

Plus d'infos: [Problèmes de sons sous Ubuntu](https://doc.ubuntu-fr.org/son_problemes)

# Affichage

## Docs de référence

https://doc.ubuntu-fr.org/resolution_ecran_avance

## Plantage interface graphique Xorg / Wayland

Basculer vers un tty avec ctrl + alt + F1 à F6 pour voir les logs sous `/var/log`

Revenir vers le bureau avec ctrl + alt + F7

Le paramètre de boot `nomodeset` semble régler pas mal de soucis de cartes graphiques qui causent des écrans noirs et/ou plantage Xorg (à changer dans les options du grub)
