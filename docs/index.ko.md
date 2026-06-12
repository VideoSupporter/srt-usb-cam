---
layout: default
---

# SRT USB CAM

> Windows용 USB 카메라 SRT MPEG-TS/H.264 실시간 송신 앱

> 언어: [English](index.md) | [Español](index.es.md) | 한국어 | [中文](index.zh.md) | [Deutsch](index.de.md) | [Français](index.fr.md) | [Italiano](index.it.md) | [Bahasa Indonesia](index.id-id.md) | [Deutsch (DE)](index.de-de.md) | [Français (FR)](index.fr-fr.md) | [Italiano (IT)](index.it-it.md)

[![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)](https://github.com/VideoSupporter/srt-usb-cam)
[![Protocol](https://img.shields.io/badge/protocol-SRT-orange.svg)](https://www.srtalliance.org/)

## 다운로드

- [Microsoft Store 무료 버전](https://apps.microsoft.com/detail/9P1TKLLFV43G) - 송신 창 1개를 실행합니다.
- [Microsoft Store PRO 버전](https://apps.microsoft.com/detail/9NMW8TT83453) - 여러 송신 창을 실행할 수 있습니다.

SRT USB CAM은 Windows에서 USB 카메라 영상을 캡처하고 MPEG-TS/H.264 스트림으로 SRT 전송하는 앱입니다.
Windows Media Foundation으로 카메라 입력과 인코딩을 처리하며, SRT 수신기에 caller 모드로 연결하기 전에 USB 오디오 입력을 AAC-LC로 MPEG-TS에 다중화할 수 있습니다.

이 제품은 무료 버전입니다. 유료 버전인 "SRT USB CAM PRO"는 여러 인스턴스 실행을 지원합니다.
https://apps.microsoft.com/detail/9NMW8TT83453

## 새로운 기능

Version 1.0.4
- USB 카메라 내장 마이크 또는 오디오 입력 장치를 선택하고 AAC-LC 오디오로 MPEG-TS에 다중화할 수 있도록 지원했습니다.
- 오디오 레벨 표시, 음소거, CH1/CH2 채널별 지연, 입력 레벨 조정을 추가했습니다. (PRO ONLY)
- Test Signal에 25 / 29.97 / 50 / 59.94 FPS와 1 kHz 테스트 오디오를 추가했습니다.
- 저장된 카메라 형식을 현재 카메라에서 사용할 수 없는 경우 Test Signal로 폴백하도록 했습니다.
- 시작 후 수동 시작 작업을 생략할 수 있도록 Auto Start 설정을 추가했습니다.

Version 1.0.3
- UI를 탭 레이아웃으로 변경하고 항목 표시와 조작을 정리해 사용성을 개선했습니다.
- 설정 내보내기/가져오기 및 stream ID 설정을 지원합니다.
- REC를 지원합니다. MPEG-TS 녹화, 녹화 폴더 선택, 녹화 파일 이름 설정을 지원하여 전송 내용을 더 쉽게 저장할 수 있습니다.
- OpenH264 인코더 선택 기능을 추가했습니다.
- MediaMTX를 지원하며, MediaMTX용 SRT 전송을 지원합니다.
- MPEG-TS null stuffing을 지원합니다.

## 주요 기능

- **USB 카메라 캡처** - 연결된 USB 카메라를 선택하고 입력 영상을 미리 봅니다.
- **실시간 SRT 전송** - MPEG-TS/H.264 영상을 SRT listener로 전송합니다.
- **AAC-LC 오디오 전송** - USB 카메라 내장 마이크 또는 오디오 입력 장치의 오디오를 MPEG-TS에 다중화합니다.
- **연결 설정** - 대상 IP 주소, 포트, 자동 재연결을 설정합니다.
- **실시간 통계** - FPS, 비트레이트, TS 패킷 수, 재연결 횟수, 최근 오류를 확인합니다.
- **MPEG-TS 녹화** - 전송 중 MPEG-TS 스트림을 파일로 저장합니다.
- **OpenH264 인코더** - OpenH264를 사용한 H.264 인코딩을 선택합니다.
- **오디오 모니터** - 오디오 레벨, 음소거, CH1/CH2 채널별 지연, 입력 레벨을 모니터링하고 조정합니다. (PRO ONLY)
- **멀티 인스턴스** - 여러 송신 창을 동시에 실행합니다. (PRO ONLY)

## 스크린샷

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

## 사용 방법

수신 PC에서 FFplay와 같은 SRT listener를 시작합니다.

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
```

USB 카메라를 선택하고 대상 IP 주소와 포트를 설정한 다음 전송을 시작합니다.

## 수신 예시

```bash
ffplay "srt://0.0.0.0:9000?mode=listener"
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -f null -
ffmpeg -i "srt://0.0.0.0:9000?mode=listener" -c copy capture.ts
```

## 시스템 요구 사항

- Windows 11 x64
- Windows Media Foundation을 지원하는 USB 카메라
- FFmpeg, FFplay 또는 기타 SRT 호환 수신기

## 참고 사항

- 앱은 SRT caller 모드로 전송합니다. 수신기는 listener로 대기해야 합니다.
- 스트림 형식은 H.264 비디오와 선택적 AAC-LC 오디오를 포함한 MPEG-TS입니다.
- 현재 버전에서는 SRT 암호화를 사용하지 않습니다.

## 지원

- [GitHub Issues](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact: videosp.info@gmail.com
