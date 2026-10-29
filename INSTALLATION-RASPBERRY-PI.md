# Installer Sally Home Connect sur un Raspberry Pi

🇬🇧 [English version](INSTALLATION-RASPBERRY-PI.en.md)

Sally vit sur un Raspberry Pi : un petit boîtier qui reste allumé jour et nuit, sans écran, sans clavier, et qui
consomme très peu.

L'installation ne demande **aucune commande** : on écrit Sally sur une carte micro-SD, on met la carte dans le
Raspberry Pi, on branche, c'est tout.

## Ce qu'il faut

- un **Raspberry Pi 4** (2 Go de mémoire ou plus) ou un **Raspberry Pi 5**, avec son alimentation officielle ;
- une **carte micro-SD** de 16 Go ou plus (32 Go conseillés), et un lecteur de cartes pour l'ordinateur ;
- un **câble réseau** pour le relier à ta box (obligatoire : le Wi-Fi ne se règle pas encore depuis cette image) ;
- tes **clés USB** Zigbee ou EnOcean, si tu as des appareils à piloter :

| Technologie | Clés reconnues |
|---|---|
| Zigbee | Sonoff ZBDongle-P, Sonoff ZBDongle-E, ConBee II |
| EnOcean | EnOcean USB 300 |

## 1. Télécharger

1. Dans l'onglet [**Releases**](../../releases/latest), télécharge le fichier de la dernière version :

   ```text
   sally-home-connect-2.0.0-raspberry-pi.img.xz
   ```

   Ne le décompresse pas : le logiciel de l'étape suivante s'en charge.
2. Installe **Raspberry Pi Imager**, le logiciel gratuit et officiel de la fondation Raspberry Pi :
   https://www.raspberrypi.com/software/

## 2. Écrire Sally sur la carte

1. Mets la carte micro-SD dans l'ordinateur. Si Windows propose de la formater : **refuse**.
2. Ouvre **Raspberry Pi Imager**.
3. **Appareil** : choisis ton modèle de Raspberry Pi.
4. **Système d'exploitation** : descends tout en bas et choisis **« Utiliser une image personnalisée »**, puis le
   fichier `sally-home-connect-…-raspberry-pi.img.xz` téléchargé.
5. **Stockage** : choisis ta carte micro-SD. Attention, tout ce qu'elle contient sera effacé.
6. Si Imager propose de **personnaliser** le système, passe cette étape : rien n'est à régler.
7. Confirme, puis attends la fin de l'écriture et de la vérification (5 à 10 minutes).

## 3. Démarrer

1. Mets la carte dans le Raspberry Pi.
2. Branche le **câble réseau** sur ta box, tes **clés USB**, puis l'**alimentation** en dernier.
3. Attends **3 minutes** : au premier démarrage, le Raspberry Pi s'installe.

## 4. Ouvrir Sally

Sur l'ordinateur ou le téléphone, connecté à la même box, ouvre :

```text
https://sally.local
```

La première fois, le navigateur affiche un avertissement : c'est normal, Sally a son propre certificat, créé chez
toi. Choisis **« Paramètres avancés »** puis **« Continuer »**.

**Si l'adresse ne s'ouvre pas** (certains antivirus ou téléphones ne connaissent pas les adresses en `.local`) :

- essaie l'**adresse fixe** que Sally prend d'elle-même : ton réseau avec la fin **.200**, le plus souvent
  `https://192.168.1.200` (ou `https://192.168.0.200`, selon ta box) ;
- ou regarde la **liste des appareils de ta box** (son application sur le téléphone, ou sa page de réglages) : le
  Raspberry Pi y apparaît sous le nom **sally**, avec son adresse (par exemple `192.168.1.39`). Tape alors
  `https://` suivi de cette adresse ;
- si tu as essayé Sally sur Windows : **Réglages → Ma Sally Raspberry → Chercher**, puis **Ouvrir**.

Garde ensuite cette adresse dans tes favoris.

## 5. Le premier démarrage

Sally t'accueille avec un petit assistant :

1. la **langue** ;
2. **récupérer la maison de ton essai sur Windows** (si tu as essayé Sally sur l'ordinateur) : sur l'ordinateur,
   **Réglages → Ma Sally Raspberry → Envoyer ma maison**. Pièces, appareils, routines, réseau Zigbee et codes
   d'accès arrivent sur le Raspberry Pi : pas besoin de réappairer tes appareils. Débranche ensuite les clés USB de
   l'ordinateur, branche-les sur le Raspberry Pi, puis redémarre-le (**Réglages → Raspberry Pi → Redémarrer**) ;
3. sinon, ton **code d'accès** : sans lui, personne ne pilote ta maison, même connecté à ton Wi-Fi. Note bien le
   **code de secours** que Sally affiche : il sert si tu oublies ton code ;
4. le **nom de ta maison** ;
5. l'**adresse de Sally**, à garder. Sur le téléphone, ouvre-la puis **« Ajouter à l'écran d'accueil »** : Sally
   s'ouvre ensuite comme une application.

Ensuite : **Réglages → Ajouter un appareil**. L'onglet **Aide** de Sally explique chaque fonction.

## Piloter la maison de l'extérieur

Sally n'a besoin d'aucun service sur Internet pour être pilotée de dehors : ton téléphone se relie directement à ta
box par un **VPN**, un tunnel chiffré. Il faut une box qui sait faire « serveur VPN » (la Freebox, par exemple).

1. **Demande à ton opérateur une adresse IP fixe.** Sans elle, l'adresse de ta box change de temps en temps et le VPN
   ne la retrouve plus. Chez Free : espace abonné → **Ma Freebox** → **Demander une adresse IP fixe V4 full-stack**
   (gratuit), puis redémarre la box.
2. Dans Sally : **Réglages → Raspberry Pi → Adresse fixe pour l'accès à distance** doit être allumé. Note l'adresse
   affichée (par exemple `https://192.168.1.200`).
3. Dans la page de ta box, ouvre **Serveur VPN** (attention : pas « Client VPN », qui fait l'inverse), choisis
   **WireGuard**, active-le, puis crée un utilisateur par téléphone.
4. Sur le téléphone, installe l'application gratuite **WireGuard**, touche **+** puis **Scanner un code QR**, et
   scanne le code de l'utilisateur affiché par la box.
5. Dehors : allume le VPN dans WireGuard, puis ouvre l'adresse notée à l'étape 2 (`sally.local` ne marche pas à
   travers le VPN).

## Éteindre proprement

Ne débranche pas le Raspberry Pi pendant qu'il écrit : **Réglages → Raspberry Pi → Éteindre**, attends que sa petite
lumière verte ne clignote plus, puis débranche-le.

## L'essai et la licence

Sally fonctionne entièrement pendant **30 jours gratuits**. Le Raspberry Pi a son propre **code d'installation** :
sa licence est faite pour lui. La vente en ligne ouvre bientôt ; d'ici là, pour continuer après l'essai, écris à
**sallyhomeconnect@gmail.com**.

## Mises à jour

Si tu autorises Sally à consulter Internet (**Réglages → Internet**), elle te prévient d'une nouvelle version dans
**Réglages → Mises à jour**. Touche **Installer la mise à jour** : Sally la vérifie, s'installe et redémarre (une
minute environ). Si la nouvelle version ne démarre pas, elle revient toute seule à la précédente.

## Vie privée

Rien ne sort de chez toi : pas de compte en ligne, pas de cloud, et Sally marche même quand Internet est coupé.
L'accès au Raspberry Pi par SSH est éteint.

## En cas de souci

- **Sally ne s'ouvre pas après 5 minutes** : vérifie que le voyant vert du Raspberry Pi clignote de temps en temps,
  que le câble réseau est bien branché sur la box, puis débranche et rebranche l'alimentation.
- **Une question** : sallyhomeconnect@gmail.com
