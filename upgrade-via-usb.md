# Upgrade via USB

## Matériel nécessaire

- Clé USB formattée en NTFS ou FAT32 avec au moins 1Go de libre (il peut y avoir d'autres fichiers dessus)

## Écriture des fichiers sur la clé

- Créer un dossier `pooliot-upgrade` a la racine
- Copier le contenu du fichier d'installation, dezippé (il doit donc y avoir un dossier `os` dans le dossier `pooliot-upgrade`)

## Upgrade d'un device

:warning: le device doit déja etre sur une version 17 ou ultérieur pour que la procédure fonctionne. Si c'est n'est pas le cas, il faudra repasser par un reformattage de la carte SD, tel que définie dans la procédure 

- Brancher la clé USB sur l'un des ports USB.
- L'écran doit immédiatement afficher un message indiquant qu'il a détecté la clé USB
- Le device va ensuite copier une partie du contenu de la clé. L'operation peut prendre un peu de temps.
- Une fois la copie terminée, le device va redémarrer et lancer la nouvelle installation. Des que le device redémarre il est possible de retirer la clé.

Si la clé n'est pas retirée, il est possible que l'installation recommence a nouveau, indéfiniment. Il est donc important de la retirer pendant l'installation !
