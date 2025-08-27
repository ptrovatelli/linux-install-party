# Boot

## Tiret blanc qui clignote / ne boot pas

Au moment de booter sur la clé, rien ne s'affiche à part un tiret blanc qui clignote. Ca indique un plantage très tôt dans le lancement. Peut-être une incompatibilité d'architecture de CPU avec la distribution de la clé usb

Autres pistes: 

- Assurez-vous que le BIOS est en UEFI si disponible (pas en Legacy)
- Désactiver le Secure Boot, désactiver les « Windows Optimized Defaults » ou d’autres options similaires.

# Son

## Pas de son

- Ouvrir alsamixer et essayer différents canaux

- Essayer avec des écouteurs (souci carte son vs souci hauts-parleurs)
