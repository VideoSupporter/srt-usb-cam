---
layout: default
---

# SRT USB CAM

> Pemancar real-time kamera USB ke SRT MPEG-TS/H.264 untuk Windows

> Bahasa: [English](index.md) | [Español](index.es.md) | [한국어](index.ko.md) | [中文](index.zh.md) | [Deutsch](index.de.md) | [Français](index.fr.md) | [Italiano](index.it.md) | Bahasa Indonesia | [Deutsch (DE)](index.de-de.md) | [Français (FR)](index.fr-fr.md) | [Italiano (IT)](index.it-it.md)

[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://github.com/VideoSupporter/srt-usb-cam)
[![Protocol](https://img.shields.io/badge/protocol-SRT-orange.svg)](https://www.srtalliance.org/)

## Unduh

- [Versi Gratis di Microsoft Store](https://apps.microsoft.com/detail/9P1TKLLFV43G) - Satu jendela transmitter.
- [Versi PRO di Microsoft Store](https://apps.microsoft.com/detail/9NMW8TT83453) - Jalankan beberapa jendela transmitter.

SRT USB CAM menangkap video dari kamera USB di Windows dan mengirimkannya sebagai stream MPEG-TS/H.264 melalui SRT.
Aplikasi ini menggunakan Windows Media Foundation untuk input kamera dan encoding, serta dapat melakukan multiplex input audio USB sebagai AAC-LC ke MPEG-TS sebelum terhubung ke penerima SRT dalam mode caller.

Produk ini adalah versi gratis. Versi berbayar, "SRT USB CAM PRO", mendukung menjalankan beberapa instance.
https://apps.microsoft.com/detail/9NMW8TT83453

## Yang Baru

Version 1.0.4
- Menambahkan dukungan untuk memilih mikrofon bawaan kamera USB atau perangkat input audio dan melakukan multiplex ke MPEG-TS sebagai audio AAC-LC.
- Menambahkan tampilan level audio, mute, delay per channel CH1/CH2, dan penyesuaian level input. (PRO ONLY)
- Menambahkan 25 / 29.97 / 50 / 59.94 FPS dan audio uji 1 kHz ke Test Signal.
- Menambahkan fallback ke Test Signal ketika format kamera yang tersimpan tidak tersedia pada kamera saat ini.
- Menambahkan pengaturan Auto Start untuk melewati operasi start manual setelah aplikasi diluncurkan.

Version 1.0.3
- UI diubah ke layout tab dan tampilan item serta kontrol disusun ulang agar lebih mudah digunakan.
- Menambahkan dukungan ekspor/impor pengaturan dan konfigurasi stream ID.
- Menambahkan dukungan REC. Perekaman MPEG-TS, pemilihan folder rekaman, dan konfigurasi nama file rekaman kini tersedia, sehingga konten streaming lebih mudah disimpan.
- Menambahkan pilihan encoder OpenH264.
- Menambahkan dukungan MediaMTX, termasuk streaming SRT untuk MediaMTX.
- Menambahkan dukungan MPEG-TS null stuffing.

## Fitur Utama

- **Capture Kamera USB** - Pilih kamera USB yang terhubung dan pratinjau video input.
- **Transmisi SRT Real-time** - Kirim video MPEG-TS/H.264 ke SRT listener.
- **Transmisi Audio AAC-LC** - Multiplex audio dari mikrofon bawaan kamera USB atau perangkat input audio ke MPEG-TS.
- **Kontrol Koneksi** - Konfigurasikan alamat IP tujuan, port, dan koneksi ulang otomatis.
- **Statistik Live** - Pantau FPS, bitrate, jumlah paket TS, jumlah koneksi ulang, dan error terbaru.
- **Perekaman MPEG-TS** - Simpan stream MPEG-TS ke file saat transmisi.
- **Encoder OpenH264** - Pilih encoding H.264 dengan OpenH264.
- **Monitor Audio** - Pantau dan sesuaikan level audio, mute, delay per channel CH1/CH2, dan level input. (PRO ONLY)
- **Multi-Instance** - Jalankan beberapa jendela transmitter secara bersamaan. (PRO ONLY)

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

## Cara Menggunakan

Mulai SRT listener pada komputer penerima, misalnya dengan FFplay:

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

Pilih kamera USB, konfigurasikan alamat IP dan port tujuan, lalu mulai transmisi.

## Contoh Penerimaan

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -f null -
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -c copy capture.ts
```

## Persyaratan Sistem

- Windows 11 x64
- Kamera USB yang didukung Windows Media Foundation
- Penerima kompatibel SRT seperti FFmpeg atau FFplay

## Catatan

- Aplikasi mengirim dalam mode SRT caller. Penerima harus menunggu sebagai listener.
- Format stream adalah MPEG-TS dengan video H.264 dan audio AAC-LC opsional.
- Enkripsi SRT tidak diaktifkan pada versi saat ini.

## Dukungan

- [GitHub Issues](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact: videosp.info@gmail.com
