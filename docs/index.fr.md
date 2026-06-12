---
layout: default
---

# SRT USB CAM

> Emetteur USB camera vers SRT MPEG-TS/H.264 en temps reel pour Windows

> Langues: [English](index.md) | [Español](index.es.md) | [한국어](index.ko.md) | [中文](index.zh.md) | [Deutsch](index.de.md) | Français | [Italiano](index.it.md) | [Bahasa Indonesia](index.id-id.md) | [Deutsch (DE)](index.de-de.md) | [Français (FR)](index.fr-fr.md) | [Italiano (IT)](index.it-it.md)

[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://github.com/VideoSupporter/srt-usb-cam)
[![Protocol](https://img.shields.io/badge/protocol-SRT-orange.svg)](https://www.srtalliance.org/)

## Telechargement

- [Version gratuite sur Microsoft Store](https://apps.microsoft.com/detail/9P1TKLLFV43G) - Une seule fenetre d emetteur.
- [Version PRO sur Microsoft Store](https://apps.microsoft.com/detail/9NMW8TT83453) - Executez plusieurs fenetres d emetteur.

SRT USB CAM capture la video d une camera USB sous Windows et l envoie sous forme de flux MPEG-TS/H.264 via SRT.
L application utilise Windows Media Foundation pour l entree camera et l encodage, et peut multiplexer l entree audio USB en AAC-LC dans MPEG-TS avant de se connecter a un recepteur SRT en mode caller.

Ce produit est la version gratuite. La version payante, "SRT USB CAM PRO", permet d executer plusieurs instances.
https://apps.microsoft.com/detail/9NMW8TT83453

## Nouveautes

Version 1.0.4
- La prise en charge de la selection du micro integre d une camera USB ou d un peripherique d entree audio et de son multiplexage en audio AAC-LC dans MPEG-TS a ete ajoutee.
- L affichage du niveau audio, la mise en sourdine, le delai par canal CH1/CH2 et le reglage du niveau d entree ont ete ajoutes. (PRO ONLY)
- 25 / 29.97 / 50 / 59.94 FPS et un audio de test 1 kHz ont ete ajoutes a Test Signal.
- Un fallback vers Test Signal a ete ajoute lorsque le format de camera enregistre n est pas disponible sur la camera actuelle.
- Des parametres Auto Start ont ete ajoutes pour ignorer l operation de demarrage manuelle apres le lancement.

Version 1.0.3
- L interface utilisateur a ete modifiee en une disposition par onglets, et l affichage des elements ainsi que les controles ont ete reorganises pour ameliorer l utilisation.
- La prise en charge de l exportation/importation des parametres et de la configuration du stream ID a ete ajoutee.
- La prise en charge REC a ete ajoutee. L enregistrement MPEG-TS, le choix du dossier d enregistrement et la configuration du nom de fichier d enregistrement sont maintenant disponibles, ce qui facilite la sauvegarde du contenu diffuse.
- La selection de l encodeur OpenH264 a ete ajoutee.
- La prise en charge de MediaMTX a ete ajoutee, y compris le streaming SRT pour MediaMTX.
- La prise en charge du null stuffing MPEG-TS a ete ajoutee.

## Fonctions principales

- **Capture de camera USB** - Selectionnez une camera USB connectee et previsualisez la video d entree.
- **Transmission SRT en temps reel** - Envoyez une video MPEG-TS/H.264 vers un SRT listener.
- **Transmission audio AAC-LC** - Multiplexez l audio d un micro integre de camera USB ou d un peripherique d entree audio dans MPEG-TS.
- **Controles de connexion** - Configurez l adresse IP de destination, le port et la reconnexion automatique.
- **Statistiques en direct** - Surveillez les FPS, le debit, le nombre de paquets TS, le nombre de reconnexions et la derniere erreur.
- **Enregistrement MPEG-TS** - Enregistrez le flux MPEG-TS dans un fichier pendant la transmission.
- **Encodeur OpenH264** - Selectionnez l encodage H.264 avec OpenH264.
- **Moniteur audio** - Surveillez et reglez le niveau audio, la mise en sourdine, le delai par canal CH1/CH2 et le niveau d entree. (PRO ONLY)
- **Multi-instance** - Executez plusieurs fenetres d emetteur en meme temps. (PRO ONLY)

## Captures d ecran

![SRT USB CAM screenshot 1](./images/screenshot.png)

![SRT USB CAM screenshot 2](./images/screenshot2.png)

![SRT USB CAM screenshot 3](./images/screenshot3.png)

![SRT USB CAM screenshot 4](./images/screenshot4.png)

![SRT USB CAM screenshot 5](./images/screenshot5.png)

![SRT USB CAM screenshot 6](./images/screenshot6.png)

![SRT USB CAM screenshot 7](./images/screenshot7.png)

![SRT USB CAM screenshot 8](./images/screenshot8.png)

![SRT USB CAM screenshot 9](./images/screenshot9.png)

![SRT USB CAM screenshot 10](./images/screenshot10.png)

## Utilisation

Demarrez un SRT listener sur la machine de reception, par exemple avec FFplay :

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

Selectionnez une camera USB, configurez l adresse IP et le port de destination, puis demarrez la transmission.

## Exemples de reception

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -f null -
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -c copy capture.ts
```

## Configuration requise

- Windows 11 x64
- Camera USB compatible avec Windows Media Foundation
- Recepteur compatible SRT tel que FFmpeg ou FFplay

## Notes

- L application envoie en mode SRT caller. Le recepteur doit attendre en mode listener.
- Le format du flux est MPEG-TS avec video H.264 et audio AAC-LC optionnel.
- Le chiffrement SRT n est pas active dans la version actuelle.

## Support

- [GitHub Issues](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact: videosp.info@gmail.com
