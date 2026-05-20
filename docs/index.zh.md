---
layout: default
---

# SRT USB Camera Transmitter

> 适用于 Windows 的 USB 摄像头 SRT MPEG-TS/H.264 实时发送工具

> Languages: [English](index.md) | [中文](index.zh.md) | [한국어](index.ko.md) | [Español](index.es.md)

[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://github.com/VideoSupporter/srt-usb-cam)
[![Protocol](https://img.shields.io/badge/protocol-SRT-orange.svg)](https://www.srtalliance.org/)

[Microsoft Store single free](https://apps.microsoft.com/detail/9P1TKLLFV43G)

[Microsoft Store multi](https://apps.microsoft.com/detail/9P9Z686RR6NJ)

SRT USB Camera Transmitter 可在 Windows 上采集 USB 摄像头视频，并通过 SRT 发送 MPEG-TS/H.264 实时流。
应用使用 Windows Media Foundation 进行摄像头输入和编码，将视频复用为 MPEG-TS，并以 SRT caller 模式连接到接收端。

## 主要功能

- **USB 摄像头采集** - 选择已连接的 USB 摄像头并预览输入视频。
- **实时 SRT 发送** - 将 MPEG-TS/H.264 视频发送到 SRT listener。
- **自动格式选择** - 优先使用 1080p60，必要时回退到 1080p30、720p30 或 640x480 30fps。
- **连接设置** - 配置目标 IP 地址、端口和自动重连。
- **实时统计** - 查看 FPS、码率、TS 包数量、重连次数和最近错误。
- **多实例版本** - 多实例版本可同时运行多个发送窗口。

## 网络配置

```mermaid
graph LR
    Camera["USB 摄像头"]
    App["SRT USB Camera Transmitter<br/>(SRT Caller)"]
    Network["网络<br/>(LAN / Internet)"]
    Receiver["SRT 接收端<br/>FFplay / FFmpeg / Decoder<br/>(SRT Listener)"]

    Camera -->|视频帧| App
    App -->|SRT + MPEG-TS/H.264| Network
    Network -->|SRT + MPEG-TS/H.264| Receiver

    style Camera fill:#D7F4D2,stroke:#3C8D40,color:#000
    style App fill:#A8D5FF,stroke:#4A90E2,color:#000
    style Receiver fill:#90CAF9,stroke:#1976D2,color:#000
    style Network fill:#FFFFFF,stroke:#CCCCCC,color:#000
```

<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
<script>mermaid.initialize({startOnLoad:true,theme:'default'});</script>

## 截图

![SRT USB Camera Transmitter](./images/screenshot.png)

## 使用方法

### 1. 启动 SRT 接收端

在接收机器上启动 SRT listener。快速测试可使用 FFplay：

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

### 2. 选择 USB 摄像头

启动 SRT USB Camera Transmitter，然后选择要发送的 USB 摄像头。
如果只连接了一台摄像头，应用可以自动选择。

### 3. 配置目标地址

输入接收端 IP 地址和端口号。
在同一台 PC 上本地测试时，可使用 `127.0.0.1`。

### 4. 开始发送

点击 **Start connection** 连接到 SRT listener 并开始发送视频。
发送过程中会更新预览和实时统计。

## 接收示例

播放视频流：

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

接收并验证视频流：

```bash
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -f null -
```

保存接收到的 MPEG-TS：

```bash
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -c copy capture.ts
```

## 系统要求

- Windows 11 x64
- Windows Media Foundation 支持的 USB 摄像头
- 支持 H.264 硬件编码的环境
- FFmpeg、FFplay 或其他兼容 SRT 的接收端

## 注意事项

- 应用以 SRT caller 模式发送。接收端必须以 listener 模式等待连接。
- 流格式为 MPEG-TS/H.264。
- 当前不包含音频发送。
- 当前版本未启用 SRT 加密。

## 支持

- [GitHub Issues](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact: videosp.info@gmail.com
