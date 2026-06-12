---
layout: default
---

# SRT USB CAM

> 适用于 Windows 的 USB 摄像头 SRT MPEG-TS/H.264 实时发送工具

> 语言: [English](index.md) | [Español](index.es.md) | [한국어](index.ko.md) | 中文 | [Deutsch](index.de.md) | [Français](index.fr.md) | [Italiano](index.it.md) | [Bahasa Indonesia](index.id-id.md) | [Deutsch (DE)](index.de-de.md) | [Français (FR)](index.fr-fr.md) | [Italiano (IT)](index.it-it.md)

[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://github.com/VideoSupporter/srt-usb-cam)
[![Protocol](https://img.shields.io/badge/protocol-SRT-orange.svg)](https://www.srtalliance.org/)

## 下载

- [Microsoft Store 免费版](https://apps.microsoft.com/detail/9P1TKLLFV43G) - 单个发送窗口。
- [Microsoft Store PRO 版](https://apps.microsoft.com/detail/9NMW8TT83453) - 可运行多个发送窗口。

SRT USB CAM 可在 Windows 上采集 USB 摄像头视频，并通过 SRT 发送 MPEG-TS/H.264 实时流。
应用使用 Windows Media Foundation 进行摄像头输入和编码，并可在以 caller 模式连接到 SRT 接收端之前，将 USB 音频输入作为 AAC-LC 复用到 MPEG-TS 中。

本产品为免费版。付费版“SRT USB CAM PRO”支持运行多个实例。
https://apps.microsoft.com/detail/9NMW8TT83453

## 更新内容

Version 1.0.4
- 支持选择 USB 摄像头内置麦克风或音频输入设备，并将其作为 AAC-LC 音频复用到 MPEG-TS 中。
- 增加音频电平显示、静音、CH1/CH2 分通道延迟和输入电平调整。 (PRO ONLY)
- 为 Test Signal 增加 25 / 29.97 / 50 / 59.94 FPS 和 1 kHz 测试音频。
- 当保存的摄像头格式在当前摄像头上不可用时，支持回退到 Test Signal。
- 增加 Auto Start 设置，可在启动后跳过手动开始操作。

Version 1.0.3
- 将 UI 改为标签页布局，并整理了各项显示和操作，提升易用性。
- 支持设置的导出/导入以及 stream ID 配置。
- 增加 REC 支持。现在支持 MPEG-TS 录制、录制文件夹选择和录制文件名配置，更便于保存传输内容。
- 增加 OpenH264 编码器选择功能。
- 增加 MediaMTX 支持，包括面向 MediaMTX 的 SRT 推流。
- 增加 MPEG-TS null stuffing 支持。

## 主要功能

- **USB 摄像头采集** - 选择已连接的 USB 摄像头并预览输入视频。
- **实时 SRT 发送** - 将 MPEG-TS/H.264 视频发送到 SRT listener。
- **AAC-LC 音频发送** - 将 USB 摄像头内置麦克风或音频输入设备的音频复用到 MPEG-TS 中。
- **连接设置** - 配置目标 IP 地址、端口和自动重连。
- **实时统计** - 查看 FPS、码率、TS 包数量、重连次数和最近错误。
- **MPEG-TS 录制** - 传输时将 MPEG-TS 流保存到文件。
- **OpenH264 编码器** - 选择使用 OpenH264 进行 H.264 编码。
- **音频监视器** - 监视并调整音频电平、静音、CH1/CH2 分通道延迟和输入电平。 (PRO ONLY)
- **多实例** - 同时运行多个发送窗口。 (PRO ONLY)

## 截图

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

## 使用方法

在接收机器上启动 SRT listener，例如使用 FFplay：

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

选择 USB 摄像头，配置目标 IP 地址和端口，然后开始发送。

## 接收示例

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -f null -
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -c copy capture.ts
```

## 系统要求

- Windows 11 x64
- Windows Media Foundation 支持的 USB 摄像头
- FFmpeg、FFplay 或其他兼容 SRT 的接收端

## 注意事项

- 应用以 SRT caller 模式发送。接收端必须以 listener 模式等待连接。
- 流格式为 MPEG-TS，包含 H.264 视频和可选 AAC-LC 音频。
- 当前版本未启用 SRT 加密。

## 支持

- [GitHub Issues](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact: videosp.info@gmail.com
