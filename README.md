# VoIP Call Voice Changer

[![CI](https://github.com/SucceedHQ-innovations/voice-changer-android/actions/workflows/ci.yml/badge.svg)](https://github.com/SucceedHQ-innovations/voice-changer-android/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.0.20-purple.svg)](https://kotlinlang.org)

**Real-time voice transformation for WhatsApp and Telegram calls.**

An Android application that modifies your voice in real-time during VoIP calls. Uses pitch shifting combined with formant preservation to produce natural-sounding voice changes with under 100ms latency.

## Features

- Real-time voice changing (Male / Female / Neutral)
- Works with WhatsApp & Telegram calls
- Low latency (<100ms)
- Natural-sounding audio quality
- Simple ON/OFF toggle interface
- Background service for seamless operation
- Python server for remote inference (optional)

## Architecture

```
Android App (Kotlin)
├── Real-time audio capture (AudioRecord)
├── Pitch + formant shifting engine
├── Background service
└── WebSocket/UDP bridge to server

Server (Python)       Web App (React/Vite)
├── RVC inference     ├── Voice configuration
├── Audio processing  └── Real-time controls
└── REST API
```

## Getting Started

### Android App

```bash
# Requirements: Java 17, Android SDK
cd android
./gradlew assembleRelease
```

APK output: `android/app/build/outputs/apk/release/app-release-unsigned.apk`

### Server

```bash
cd server
pip install -r requirements.txt
python main.py
```

### Web App

```bash
cd web-app
npm install
npm run dev
```

## Usage

1. Install the APK on your Android device
2. Open "Call Voice Changer"
3. Grant microphone permission
4. Select voice mode (Male / Female / Neutral)
5. Toggle ON
6. Make a WhatsApp or Telegram call — your voice will be transformed

## Tech Stack

- **Android:** Kotlin 2.0.20, Jetpack Compose
- **Server:** Python (RVC inference + audio processing)
- **Web:** React, Vite, JavaScript
- **Audio:** Real-time pitch shifting with formant preservation

## License

MIT
