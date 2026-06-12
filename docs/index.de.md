---
layout: default
---

# SRT USB CAM

> Echtzeit-USB-Kamera-zu-SRT-MPEG-TS/H.264-Sender fur Windows

> Sprachen: [English](index.md) | [Español](index.es.md) | [한국어](index.ko.md) | [中文](index.zh.md) | Deutsch | [Français](index.fr.md) | [Italiano](index.it.md) | [Bahasa Indonesia](index.id-id.md) | [Deutsch (DE)](index.de-de.md) | [Français (FR)](index.fr-fr.md) | [Italiano (IT)](index.it-it.md)

[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://github.com/VideoSupporter/srt-usb-cam)
[![Protocol](https://img.shields.io/badge/protocol-SRT-orange.svg)](https://www.srtalliance.org/)

## Download

- [Kostenlose Version im Microsoft Store](https://apps.microsoft.com/detail/9P1TKLLFV43G) - Ein einzelnes Senderfenster.
- [PRO-Version im Microsoft Store](https://apps.microsoft.com/detail/9NMW8TT83453) - Mehrere Senderfenster ausfuhren.

SRT USB CAM erfasst Videos von einer USB-Kamera unter Windows und sendet sie als MPEG-TS/H.264-Stream uber SRT.
Die App verwendet Windows Media Foundation fur Kameraeingabe und Codierung und kann USB-Audioeingang als AAC-LC in MPEG-TS multiplexen, bevor sie sich im SRT caller-Modus mit einem Empfanger verbindet.

Dieses Produkt ist die kostenlose Version. Die kostenpflichtige Version "SRT USB CAM PRO" unterstutzt die Ausfuhrung mehrerer Instanzen.
https://apps.microsoft.com/detail/9NMW8TT83453

## Neuigkeiten

Version 1.0.4
- Unterstutzung fur die Auswahl eines integrierten USB-Kamera-Mikrofons oder eines Audioeingabegerats und das Multiplexen als AAC-LC-Audio in MPEG-TS wurde hinzugefugt.
- Audiopegelanzeige, Stummschaltung, kanalbezogene CH1/CH2-Verzogerung und Eingangspegelanpassung wurden hinzugefugt. (PRO ONLY)
- 25 / 29.97 / 50 / 59.94 FPS und 1-kHz-Testaudio wurden zu Test Signal hinzugefugt.
- Fallback auf Test Signal wurde hinzugefugt, wenn das gespeicherte Kameraformat auf der aktuellen Kamera nicht verfugbar ist.
- Auto Start-Einstellungen wurden hinzugefugt, um den manuellen Startvorgang nach dem Start der App zu uberspringen.

Version 1.0.3
- Die Benutzeroberflache wurde auf ein Tab-Layout umgestellt, und Anzeige sowie Bedienung der Elemente wurden fur bessere Benutzerfreundlichkeit neu organisiert.
- Unterstutzung fur Export/Import von Einstellungen und die Konfiguration der stream ID wurde hinzugefugt.
- REC-Unterstutzung wurde hinzugefugt. MPEG-TS-Aufzeichnung, Auswahl des Aufnahmeordners und Konfiguration des Aufnahmedateinamens sind jetzt verfugbar, sodass gestreamte Inhalte einfacher gespeichert werden konnen.
- Auswahl des OpenH264-Encoders wurde hinzugefugt.
- MediaMTX-Unterstutzung wurde hinzugefugt, einschliesslich SRT-Streaming fur MediaMTX.
- Unterstutzung fur MPEG-TS null stuffing wurde hinzugefugt.

## Hauptfunktionen

- **USB-Kameraerfassung** - Wahlen Sie eine angeschlossene USB-Kamera aus und zeigen Sie eine Vorschau des Eingangsvideos an.
- **SRT-Ubertragung in Echtzeit** - Senden Sie MPEG-TS/H.264-Video an einen SRT listener.
- **AAC-LC-Audioubertragung** - Multiplexen Sie Audio von einem integrierten USB-Kamera-Mikrofon oder Audioeingabegerat in MPEG-TS.
- **Verbindungssteuerung** - Konfigurieren Sie Ziel-IP-Adresse, Port und automatische Wiederverbindung.
- **Live-Statistiken** - Uberwachen Sie FPS, Bitrate, TS-Paketanzahl, Wiederverbindungsanzahl und den neuesten Fehler.
- **MPEG-TS-Aufzeichnung** - Speichern Sie den MPEG-TS-Stream wahrend der Ubertragung in einer Datei.
- **OpenH264-Encoder** - Wahlen Sie H.264-Codierung mit OpenH264.
- **Audiomonitor** - Uberwachen und passen Sie Audiopegel, Stummschaltung, kanalbezogene CH1/CH2-Verzogerung und Eingangspegel an. (PRO ONLY)
- **Multi-Instanz** - Fuhren Sie mehrere Senderfenster gleichzeitig aus. (PRO ONLY)

## Screenshots

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

## Verwendung

Starten Sie auf dem Empfangsrechner einen SRT listener, zum Beispiel mit FFplay:

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

Wahlen Sie eine USB-Kamera, konfigurieren Sie Ziel-IP-Adresse und Port, und starten Sie die Ubertragung.

## Empfangsbeispiele

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -f null -
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -c copy capture.ts
```

## Systemanforderungen

- Windows 11 x64
- USB-Kamera mit Windows Media Foundation-Unterstutzung
- SRT-kompatibler Empfanger wie FFmpeg oder FFplay

## Hinweise

- Die App sendet im SRT caller-Modus. Der Empfanger muss als listener warten.
- Das Streamformat ist MPEG-TS mit H.264-Video und optionalem AAC-LC-Audio.
- SRT-Verschlusselung ist in der aktuellen Version nicht aktiviert.

## Support

- [GitHub Issues](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact: videosp.info@gmail.com
