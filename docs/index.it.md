---
layout: default
---

# SRT USB CAM

> Trasmettitore in tempo reale da videocamera USB a SRT MPEG-TS/H.264 per Windows

> Lingue: [English](index.md) | [Español](index.es.md) | [한국어](index.ko.md) | [中文](index.zh.md) | [Deutsch](index.de.md) | [Français](index.fr.md) | Italiano | [Bahasa Indonesia](index.id-id.md) | [Deutsch (DE)](index.de-de.md) | [Français (FR)](index.fr-fr.md) | [Italiano (IT)](index.it-it.md)

[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://github.com/VideoSupporter/srt-usb-cam)
[![Protocol](https://img.shields.io/badge/protocol-SRT-orange.svg)](https://www.srtalliance.org/)

## Download

- [Versione gratuita su Microsoft Store](https://apps.microsoft.com/detail/9P1TKLLFV43G) - Una sola finestra di trasmissione.
- [Versione PRO su Microsoft Store](https://apps.microsoft.com/detail/9NMW8TT83453) - Esegui piu finestre di trasmissione.

SRT USB CAM acquisisce video da una videocamera USB su Windows e lo invia come flusso MPEG-TS/H.264 tramite SRT.
L app usa Windows Media Foundation per l ingresso della videocamera e la codifica, e puo multiplexare l ingresso audio USB come AAC-LC in MPEG-TS prima di connettersi a un ricevitore SRT in modalita caller.

Questo prodotto e la versione gratuita. La versione a pagamento, "SRT USB CAM PRO", supporta l esecuzione di piu istanze.
https://apps.microsoft.com/detail/9NMW8TT83453

## Novita

Version 1.0.4
- E stato aggiunto il supporto per selezionare il microfono integrato di una videocamera USB o un dispositivo di ingresso audio e multiplexarlo in MPEG-TS come audio AAC-LC.
- Sono stati aggiunti visualizzazione del livello audio, mute, ritardo per canale CH1/CH2 e regolazione del livello di ingresso. (PRO ONLY)
- Sono stati aggiunti 25 / 29.97 / 50 / 59.94 FPS e audio di test a 1 kHz a Test Signal.
- E stato aggiunto il fallback a Test Signal quando il formato della videocamera salvato non e disponibile sulla videocamera attuale.
- Sono state aggiunte impostazioni Auto Start per saltare l operazione manuale di avvio dopo il lancio.

Version 1.0.3
- L interfaccia utente e stata modificata con un layout a schede, e la visualizzazione degli elementi e i controlli sono stati riorganizzati per migliorare l usabilita.
- E stato aggiunto il supporto per esportazione/importazione delle impostazioni e configurazione dello stream ID.
- E stato aggiunto il supporto REC. Registrazione MPEG-TS, selezione della cartella di registrazione e configurazione del nome file di registrazione sono ora disponibili, rendendo piu semplice salvare il contenuto trasmesso.
- E stata aggiunta la selezione dell encoder OpenH264.
- E stato aggiunto il supporto MediaMTX, incluso lo streaming SRT per MediaMTX.
- E stato aggiunto il supporto al null stuffing MPEG-TS.

## Funzioni principali

- **Acquisizione da videocamera USB** - Seleziona una videocamera USB collegata e visualizza l anteprima del video in ingresso.
- **Trasmissione SRT in tempo reale** - Invia video MPEG-TS/H.264 a un SRT listener.
- **Trasmissione audio AAC-LC** - Multiplexa in MPEG-TS l audio da un microfono integrato di videocamera USB o da un dispositivo di ingresso audio.
- **Controlli di connessione** - Configura indirizzo IP di destinazione, porta e riconnessione automatica.
- **Statistiche live** - Monitora FPS, bitrate, conteggio pacchetti TS, riconnessioni e ultimo errore.
- **Registrazione MPEG-TS** - Salva lo stream MPEG-TS in un file durante la trasmissione.
- **Encoder OpenH264** - Seleziona la codifica H.264 con OpenH264.
- **Monitor audio** - Monitora e regola livello audio, mute, ritardo per canale CH1/CH2 e livello di ingresso. (PRO ONLY)
- **Multi-istanza** - Esegui piu finestre di trasmissione contemporaneamente. (PRO ONLY)

## Screenshot

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

## Come usare

Avvia un SRT listener sul computer ricevente, ad esempio con FFplay:

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

Seleziona una videocamera USB, configura IP e porta di destinazione, quindi avvia la trasmissione.

## Esempi di ricezione

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -f null -
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -c copy capture.ts
```

## Requisiti di sistema

- Windows 11 x64
- Videocamera USB supportata da Windows Media Foundation
- Ricevitore compatibile SRT come FFmpeg o FFplay

## Note

- L app invia in modalita SRT caller. Il ricevitore deve restare in ascolto come listener.
- Il formato dello stream e MPEG-TS con video H.264 e audio AAC-LC opzionale.
- La crittografia SRT non e abilitata nella versione corrente.

## Supporto

- [GitHub Issues](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact: videosp.info@gmail.com
