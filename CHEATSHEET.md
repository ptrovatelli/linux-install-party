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

Exemples (il faut d'abord trouver la bonne partition...): 

## Trouver la bonne partition

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

Au boot, on peut faire une détection des composants hardware (cpu, ram, disques...) en selectionnant *utilities*, puis *Hardware detection tool*

Permet notamment de vérifier si le disque est partitionné en MBR ou GPT

Attendu après l'installation linux mint en version 22:

- MBR: Grub 2
- Partition 1:  type: GPT

=> la partition est de type GPT mais il y a aussi un MBR installé pour les systèmes legacy

Si ce n'est pas le cas, c'est que l'installation du planter avant d'arriver à son terme.



Il y a également un utilitaire d'analyse de RAM (memtest)

# Scanners et imprimantes sur ubuntu

## Scanners

https://doc.ubuntu-fr.org/scanner

## Imprimantes

https://doc.ubuntu-fr.org/imprimante
