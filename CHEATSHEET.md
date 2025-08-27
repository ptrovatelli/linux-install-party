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

[Ref](https://cp.vcclhosting.com/index.php?rp=%2Fknowledgebase%2F15%2FUsing-Finnix-Rescue-CD-to-Rescue-Repair-or-Backup-Your-Linux-System.html&&systpl=hexa)

Plutôt pour manipuler un système linux que Windows

Exemples: 

- Mot de passe root oublié

```
mount /dev/vda1 /mnt 
chroot /mnt passwd
```

- Vérifier et réparer le disque

```
fsck -y /dev/vda1
```

- Regarder le contenu du disque

```
mount /dev/vda1 /mnt 
cd /mnt
```

