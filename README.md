
# MusicDJ Studio for Android

A modern, touch-optimized web recreation of the legendary **Sony Ericsson MusicDJ™** 4-track groovebox, reimagined with **Material Design 3 (Android 14+)** UI, crisp vector SVG iconography, high-precision Web Audio API rendering, and native mobile sharing.

---

## ✨ Features

- **Material 3 Android UI**: Clean dark theme (`100dvh` viewport, notch safe-area handling, bottom sheets, elevation surfaces, and pure vector SVG iconography).
- **100% Touch-Optimized Workflow**:
  - Tap any step cell to open the categorized Sound Point picker bottom sheet.
  - Long-press any step cell to quickly clear it.
  - Smooth horizontal scrolling for infinite timeline arrangements.
  - Mechanical haptic vibration feedback (`navigator.vibrate`) on touch gestures.
- **4-Track Step Sequencer**:
  - 🥁 **Track 1:** Drums (`#ef5350`)
  - 🎸 **Track 2:** Bass (`#42a5f5`)
  - 🎹 **Track 3:** Chords (`#66bb6a`)
  - 🎺 **Track 4:** Accents (`#ffa726`)
- **Sound Point Library**: 32 categorized sound blocks spanning *Intro*, *Verse*, *Chorus*, *Break*, and *Outro*.
- **Offline Audio Mastering Engine**: Renders full songs faster than real-time using `OfflineAudioContext` directly to high-fidelity stereo **WAV audio blobs**.
- **Real-Time Visualizer & Now Playing Deck**: Animated vinyl record display with live `<canvas>` waveform bars.
- **Android Sharing & Export**:
  - Native Web Share API integration (share `.wav` directly to WhatsApp, Drive, Telegram, etc.).
  - Direct `.wav` audio download fallback.
  - Native `.mdj` project file import and export.
- **Hybrid Audio Engine with Synth Fallback**: Loads authentic sample packs (`.ogg` / `.mp3`) and automatically falls back to an internal real-time synthesizer if external audio files are missing.

---

## 📁 Directory Structure

```
├── index.html          # Complete single-file Android application
├── README.md           # Documentation & instructions
└── data/               # (Optional) Audio sample assets
    ├── 0/              # Track 0: Drums (1.ogg - 32.ogg / .mp3)
    ├── 1/              # Track 1: Bass (1.ogg - 32.ogg / .mp3)
    ├── 2/              # Track 2: Chords (1.ogg - 32.ogg / .mp3)
    └── 3/              # Track 3: Accents (1.ogg - 32.ogg / .mp3)
```

> **Note:** Even without the `data/` folder, the built-in procedural synthesizer generates sound dynamically so the app is 100% functional out-of-the-box.

---

## 🚀 Getting Started

### 1. Run Locally
Because modern browsers enforce CORS restrictions on Web Audio / Web Workers, run `index.html` via any local HTTP server:

```bash
# Using Python 3
python -m http.server 8080

# Using Node.js (npx)
npx serve .

# Using PHP
php -S localhost:8080
```

Open your browser (or mobile device connected to your local network) at:
```
http://localhost:8080
```

### 2. Run on Android Devices
- **Chrome / Firefox / Samsung Internet:** Navigate to the hosted URL. You can use **"Add to Home screen"** to install it as a standalone PWA.
- **Cordova / Capacitor / Android WebView:** Drop `index.html` into your `www/` or `dist/` asset folder to compile into a native `.apk`.

---

## 🎮 Controls & Gestures

| Action | Touch Gesture | Desktop Keyboard |
| :--- | :--- | :--- |
| **Play / Pause** | Tap the Floating Action Button (FAB) | <kbd>Space</kbd> or <kbd>1</kbd> |
| **Stop** | Tap the Stop button in the transport bar | <kbd>#</kbd> or <kbd>Esc</kbd> |
| **Assign Sound** | Tap on any grid step cell | <kbd>Enter</kbd> / Click |
| **Clear Step** | Long-press (context menu) on a cell | <kbd>Delete</kbd> |
| **Extend Timeline**| Tap the `+4 Bars` button | — |
| **Change Tempo** | Tap the BPM chip or top Tempo button | Slider / Stepper buttons |
| **Project Menu** | Tap the `⋮` top menu button | — |

---

## 💾 File Format Support

- **`.mdj` (MusicDJ Project File):** JSON-compatible schema storing track matrix data, tempo, name, and format revision. Fully portable across mobile and desktop.
- **`.wav` (PCM 16-Bit Audio):** 44.1 kHz, 16-bit stereo standard audio file master exported directly from the device.

---

## 📱 Browser Compatibility

- **Android:** Chrome 80+, Samsung Internet, Firefox Mobile, Opera Mobile.
- **iOS:** Safari 14.5+ (WebKit AudioContext compatible).
- **Desktop:** Chrome, Edge, Firefox, Brave, Safari.

---

## 📄 License

Open-source under the [MIT License](LICENSE). Inspired by Sony Ericsson's iconic feature-phone music tools.
