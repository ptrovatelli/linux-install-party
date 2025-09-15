# Langues

### Disposition du clavier

- En ligne de commande: 

```
loadkeys fr
```

- Dans linux mint: 
  - Menu / keyboard / layout / keyboard layout
    - Choisir `French (AZERTY)`

# Langue de linux mint

- Menu / Language settings
  - Language: `French, France`
  - Region: `French, France`
  - Time format: `French, France`
  - System locale : cliquer sur `Apply System-Wide`

NB: certains éléments ne seront pas modifiés avant une re-ouverture de session

# Finnix

## Intro

[Ref](https://cp.vcclhosting.com/index.php?rp=%2Fknowledgebase%2F15%2FUsing-Finnix-Rescue-CD-to-Rescue-Repair-or-Backup-Your-Linux-System.html&&systpl=hexa)

Permet de dépanner un système linux

## Installation

Il y a un petit bug sur la détection du matériel avec HDT sur finnix version. 

Après avoir flashé la clé, télécharger le fichier [pci.ids](https://github.com/pciutils/pciids/blob/master/pci.ids) et le déposer sous `isolinux` pour avoir une détection correcte des périphériques PCI

## Trouver la bonne partition

Trouver le bon disque / la bonne partition

```
lshw -class disk
lsblk
```

Monter le disque et vérifier le contenu du répertoire /home:

```
mount /dev/sda3 /mnt 
ls /mnt/home
```

## Mot de passe root oublié

```
mount /dev/sda3 /mnt 
chroot /mnt passwd
```

## Vérifier et réparer le disque

```
fsck -y /dev/sda3
```

## Analyse hardware

Au boot, on peut faire une détection des composants hardware (cpu, ram, disques...) en sélectionnant *utilities*, puis *Hardware detection tool*

### Disque

Permet notamment de vérifier si le disque est partitionné en MBR ou GPT

Attendu après l'installation linux mint en version 22:

- MBR: Grub 2
- Partition 1:  type: GPT

=> la partition est de type GPT mais il y a aussi un MBR installé pour les systèmes legacy

Si ce n'est pas le cas, c'est que l'installation du planter avant d'arriver à son terme.

### GPU

La carte graphique se trouve dans les périphériques  PCI

Ou bien lancer le live puis: 

```
lshw -c video
```



### Test de RAM

Il y a également un utilitaire d'analyse de RAM (memtest)

# Grub

## Entrer sur le menu grub

Appuyer plusieurs fois sur la touche, ne pas maintenir.

Si la touche est la même que pour les options de boot du bios, re-appuyer après être sorti des options de bios.

- cas boot en mode bios (legacy): shift
- cas boot en UEFI (matériel plus récent): esc

## Modifier les options de boot

[ref](https://doc.ubuntu-fr.org/kernel#modifier_les_parametres_du_noyau_pour_un_systeme_installe_sur_disque)

- temporairement: Sélectionner le kernel voulu dans la liste du menu grub, puis appuyer sur e pour éditer les paramètres de lancement.
- définitivement: éditer `/etc/default/grub` puis 

```
sudo update-grub
```

- depuis une session live voir [ici](https://doc.ubuntu-fr.org/kernel#modifier_les_parametres_du_noyau_pour_une_session-live)

## Re-installer grub depuis une session live

https://linuxmint-installation-guide.readthedocs.io/en/latest/multiboot.html

# Display / GPU

## driver utilisé

```
lshw -c video
```

chercher la ligne "configuration". Le pilote chargé est préfixé par "driver=". Exemple:

```
configuration: driver=i915 latency=0
```

plus d'infos sur le driver: 

```
modinfo i915
```

ou

```
modinfo $(modprobe --resolve-alias i915)
```

[ref](https://askubuntu.com/questions/23238/how-can-i-find-what-video-driver-is-in-use-on-my-system)

# Scanners et imprimantes sur ubuntu

## Scanners

https://doc.ubuntu-fr.org/scanner

## Imprimantes

https://doc.ubuntu-fr.org/imprimante
