---
layout: default
---

# SRT USB CAM

> Real-time USB camera to SRT MPEG-TS/H.264 transmitter for Windows

> Languages: English | [Español](index.es.md) | [한국어](index.ko.md) | [中文](index.zh.md) | [Deutsch](index.de.md) | [Français](index.fr.md) | [Italiano](index.it.md) | [Bahasa Indonesia](index.id-id.md) | [Deutsch (DE)](index.de-de.md) | [Français (FR)](index.fr-fr.md) | [Italiano (IT)](index.it-it.md)

[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://github.com/VideoSupporter/srt-usb-cam)
[![Protocol](https://img.shields.io/badge/protocol-SRT-orange.svg)](https://www.srtalliance.org/)

## Download

- [Free Version on Microsoft Store](https://apps.microsoft.com/detail/9P1TKLLFV43G) - Single transmitter window.
- [PRO Version on Microsoft Store](https://apps.microsoft.com/detail/9NMW8TT83453) - Run multiple transmitter windows.

SRT USB CAM captures video from a USB camera on Windows and sends it as an MPEG-TS/H.264 stream over SRT.
It uses Windows Media Foundation for camera input and encoding, and can multiplex USB audio input as AAC-LC into MPEG-TS before connecting to an SRT receiver in caller mode.

This product is the free version. The paid version, "SRT USB CAM PRO," supports running multiple instances.
https://apps.microsoft.com/detail/9NMW8TT83453

## What's New

Version 1.0.4
- Added support for selecting a USB camera built-in microphone or audio input device and multiplexing it into MPEG-TS as AAC-LC audio.
- Added audio level display, mute, per-channel CH1/CH2 delay, and input level adjustment. (PRO ONLY)
- Added 25 / 29.97 / 50 / 59.94 FPS and 1 kHz test audio to Test Signal.
- Added fallback to Test Signal when the saved camera format is not available on the current camera.
- Added Auto Start settings to skip the manual start operation after launch.

Version 1.0.3
- Changed the UI to a tabbed layout and reorganized item display and controls for better usability.
- Added support for settings export/import and stream ID configuration.
- Added REC support. MPEG-TS recording, recording folder selection, and recording file name configuration are now available, making it easier to save streamed content.
- Added OpenH264 encoder selection.
- Added MediaMTX support, including SRT streaming for MediaMTX.
- Added MPEG-TS null stuffing support.

## Key Features

- **USB Camera Capture** - Select a connected USB camera and preview the input video.
- **Real-time SRT Transmission** - Send MPEG-TS/H.264 video to an SRT listener.
- **AAC-LC Audio Transmission** - Multiplex audio from a USB camera built-in microphone or audio input device into MPEG-TS.
- **Connection Controls** - Configure destination IP address, port, and automatic reconnection.
- **Live Statistics** - Monitor FPS, bitrate, TS packet count, reconnection count, and the latest error.
- **MPEG-TS Recording** - Save the MPEG-TS stream to a file while transmitting.
- **OpenH264 Encoder** - Select H.264 encoding with OpenH264.
- **Audio Monitor** - Monitor and adjust audio level, mute, per-channel CH1/CH2 delay, and input level. (PRO ONLY)
- **Multi-Instance** - Run multiple transmitter windows at the same time. (PRO ONLY)

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

## How to Use

Start an SRT listener on the receiving machine, for example with FFplay:

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

Select a USB camera, configure the destination IP address and port, then start transmission.

## Receiver Examples

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -f null -
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -c copy capture.ts
```

## System Requirements

- Windows 11 x64
- USB camera supported by Windows Media Foundation
- SRT-compatible receiver such as FFmpeg, FFplay, or another SRT decoder

## Notes

- The app sends in SRT caller mode. The receiver must listen before or during connection.
- The stream format is MPEG-TS with H.264 video and optional AAC-LC audio.
- SRT encryption is not enabled in the current version.

## Support

- [GitHub Issues](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact: videosp.info@gmail.com
