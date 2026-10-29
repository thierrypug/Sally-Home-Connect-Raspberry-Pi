# Sally Home Connect — Raspberry Pi

🇬🇧 [English version](README.en.md)

**Ta maison connectée, sans travaux, et tes données restent chez toi.**

Sally Home Connect pilote tes lumières, prises, volets et chauffage depuis ton téléphone et ton ordinateur,
**100 % en local** : pas de compte en ligne, pas de cloud, aucune donnée de ta maison ne sort de chez toi.

Cette version s'installe sur un **Raspberry Pi**, qui reste allumé jour et nuit, sans écran ni clavier.
Tu préfères d'abord essayer sur ton ordinateur ? Voir la [bêta Windows](https://github.com/thierrypug/Sally-Home-Connect-Windows-Beta).

## Télécharger

👉 [**Télécharger la dernière version**](../../releases/latest) : fichier `sally-home-connect-….-raspberry-pi.img.xz`

- **30 jours d'essai gratuit**, avec toutes les fonctions
- **Aucune commande** : une image à écrire sur une carte micro-SD avec Raspberry Pi Imager
- Raspberry Pi 4 ou 5, carte micro-SD de 16 Go ou plus, **câble réseau**
- Interface en français, anglais, espagnol, italien et allemand

Le guide pas à pas : [INSTALLATION-RASPBERRY-PI.md](INSTALLATION-RASPBERRY-PI.md)

## Ce que Sally sait faire

- Tableau de bord simple, sur téléphone, tablette et ordinateur
- Lumières, prises, volets roulants, chauffage (fil pilote et thermostats), capteurs
- **Ajout guidé** des appareils : on choisit ce qu'on ajoute, puis la marque, et Sally lit la bonne manipulation
- Routines (« quand… si… alors… »), ambiances, chauffage programmé à la semaine
- Modes de la maison : présent, absent, nuit, vacances (avec présence simulée)
- Suivi de l'énergie et de son coût (heures pleines et creuses)
- Alertes dites à voix haute : fuite d'eau, fumée, pile faible, appareil qui ne répond plus
- **Code d'accès** et comptes pour la famille, accès invité limité dans le temps, invitation par QR code
- **Commande vocale dans les 5 langues, qui fonctionne sans Internet** : la voix ne quitte jamais la maison
- **La vie de famille** : messages entre habitants, rappels, réveil sans sonnerie, « bonne nuit », « je pars / je rentre », liste de courses partagée
- **Sally te fait économiser** : chauffage coupé quand une fenêtre reste ouverte, lumières oubliées éteintes, bilan du mois en euros
- **Piloter de l'extérieur** avec le VPN de ta box, sans aucun service extérieur (adresse fixe prise toute seule)
- Sauvegarde en un fichier, mises à jour d'un bouton, bouton « Éteindre »

## Matériel compatible

| Technologie | Clés reconnues |
|---|---|
| Zigbee | Sonoff ZBDongle-P, Sonoff ZBDongle-E, ConBee II |
| EnOcean | EnOcean USB 300 |

Plusieurs milliers d'appareils Zigbee sont reconnus (Philips Hue, IKEA, Aqara, Sonoff, NodOn, Legrand…),
grâce à une bibliothèque fournie avec Sally : aucune recherche sur Internet. Modules EnOcean essayés : NodOn
(interrupteurs sans pile, contacts de fenêtre, volets).

## Une domotique vraiment locale

- Aucun compte en ligne, aucun abonnement, aucun service cloud.
- Tout fonctionne sans Internet.
- Sally ne consulte jamais Internet sans ton accord. Seules la météo et la recherche de mises à jour peuvent l'être,
  si tu l'autorises dans les Réglages.

## Bon à savoir

- Ta maison est protégée par un code d'accès, choisi au premier démarrage.
- Tu as essayé la bêta Windows ? Ta maison passe sur le Raspberry Pi en un bouton, sans réappairer tes appareils.
- Sally est fournie **telle quelle, sans garantie** pendant l'essai. Elle ne collecte aucune donnée.
- La vente en ligne ouvre bientôt ; d'ici là, pour continuer après les 30 jours, écris à **sallyhomeconnect@gmail.com**.

## Donner ton avis

Ce qui marche, ce qui bloque, ce qui manque, ton matériel… tout nous intéresse :
onglet [Issues](../../issues) ou **sallyhomeconnect@gmail.com**

## Droits

Sally Home Connect est un logiciel protégé par le droit d'auteur. Il est interdit de le modifier, de le copier ou de
le redistribuer sans l'accord de son auteur.
