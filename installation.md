# Installation

## Matériel nécessaire

- Raspberry ([Pi 3 Modele B](https://amzn.to/2M3CnbP) ou [Pi 4 Modele B](https://amzn.to/3sTwXRd) sur Amazon)
- Alimentation et dissipateurs ([Alimentation + dissipateurs AUKRU](https://amzn.to/39ShBnm) sur Amazon)
- Carte micro SD de 8Go min homologuée [A1 + U3](https://en.wikipedia.org/wiki/Secure_Digital#Speeds) minimum (exemple: [microsd SCANDISC 32 Go pour 12euros](https://amzn.to/39foS1L) sur Amazon)
- Le zip fourni par Chris

Notez que ce sont des liens de partenaire Amazon

## Quelques règles

- Toujours brancher le cable HDMI avant l'alimentation (sinon la sortie vidéo n'a pas la bonne résolution)
- Toujours utiliser "Eteindre" dans l'interface puis attendre que la LED verte arrete de clignoter avant de débrancher une RPI. Le contraire peut rendre la carte SD corrompue et entrainer des mauvais fonctionnement tel que page web qui ne s'ouvre pas à chaque fois, certaines page plantent sans raison, voir meme impossible de démarrer. Dans ce cas, il faudra réécrire la carte, ou la changer.
- **Ne pas utiliser l'alimentation USB de la TV** pour alimenter la RPI pour 2 raisons: 1/ souvent l'alimentation ne suffit pas pour alimenter la rpi (ca marchotte mais ca peut poser des problèmes pour les videos et la longévité de la rpi) et 2/ lorsqu'on coupe la tv, l'alimentation USB va couper résultant en un arret brutal (cf point précédent)

https://www.raspberrypi.org/documentation/faqs/#pi-power

## Configuration des écrans

Si c'est une TV, il y a probablement une mise en veille automatique. Il faut la désactiver dans la configuration ! La TV s'allumera et s'eteindra controlée par la RPI via CEC.
Pour les écrans normaux, la plupart n'ont pas de mise en veille automatique. L'écran s'allume et s'éteint automatiquement lorsque le HDMI est utilisé ou coupé.

## Écriture de la carte SD

Note: si la carte SD fait plus de 32GO, suivre https://www.raspberrypi.org/documentation/installation/sdxc_formatting.md.

- Installer le logiciel pour formatter la carte SD sur windows ou mac: https://www.sdcard.org/downloads/formatter/ ou utiliser gparted sur linux.
- Formater la carte SD (en une seule partition FAT32 - avec le logiciel, il suffit de sélectionner la premiere partition correspondant a la carte SD.)
- Si nécessaire, dezipper le fichier contenant la derniere version de PooliotOS
- Copier l'intégralité du contenu dans la carte SD.

Ensuite, il faut brancher la carte SD puis mettre l'alimentation. L'installation peut prendre plusieurs minutes.

## Config optionnelle

### Edition de wpa_supplicant.conf

- Forcer la config wifi en 5Gz

```
country=FR
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
  ssid="SSID"
  psk="PASSPHRASE"
  freq_list=2412 2437 2462
}
```

## boot.txt

Une fois l'installation achevée, il est possible d'éteindre l'appareil (via l'interface) puis de reprendre la carte SD. Il y aura alors une partion nommée boot accessible.

- Désactiver la carte wifi interne (ethernet / wifi usb)

```
# disable internal wifi
dtoverlay=pi3-disable-wifi
```
