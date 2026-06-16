<div align="center">

<img src="./assets/icons/nastech_tree.png" alt="NasBeat Logo" width="120">

# NasBeat

**A unified local and plugin-first streaming music player built with Flutter & Rust.**

<p align="center">
<a href="https://github.com/ncntech/NasBeat/releases/latest"><img alt="GitHub Downloads" src="https://img.shields.io/github/downloads/ncntech/NasBeat/total?style=for-the-badge&label=DOWNLOADS" /></a>
<a href="https://github.com/ncntech/NasBeat/releases/latest"><img alt="GitHub Release" src="https://img.shields.io/github/v/release/ncntech/NasBeat?display_name=release&style=for-the-badge&color=f01d7c" /></a>
<img alt="GitHub License" src="https://img.shields.io/github/license/ncntech/NasBeat?style=for-the-badge&color=1881cc" />
<br/>
<img src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white" />
<img src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" />
<img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />
<img src="https://img.shields.io/badge/macOS-000000?style=for-the-badge&logo=apple&logoColor=white" />
</p>

**NasBeat** is an open-source music player that gives you absolute freedom over your audio. Seamlessly mix your **local device music** with an infinite universe of streams powered by a secure, **Rust-backed plugin system**. No ads, no interruptions — just your tunes, your way. 🎵

</div>

<div align="center">
  <p float="left">
    <img src="./assets/docs/playlistview.png" width="48%" />
    <img src="./assets/docs/artistview.png" width="48%" />
  </p>
  <p float="left">
    <img src="./assets/docs/playerview.png" width="48%" />
    <img src="./assets/docs/lyricsview1.png" width="48%" />
  </p>
</div>

---

## 🚀 Features

- [x] 🚫 **Ad-Free Experience:** Zero interruptions, just pure music.
- [x] 🦀 **Plugin System:** Secure, auto-updating `.bex` plugin system built with Rust.
- [x] 📂 **Local Music:** Play offline music seamlessly alongside online streams.
- [x] 🎤 **Karaoke-Style Lyrics:** Time-synced lyrics with manual offset adjustment.
- [x] 🎛️ **Audio Equalizer:** Built-in equalizer and customizable crossfade transitions.
- [x] 🔄 **Smart Replace:** Auto-recovery finds working streams if a track goes dead.
- [x] 📊 **Last.fm Scrobbling:** Automatically log your listening history.
- [x] 🎮 **Discord Rich Presence:** Show your current tunes on Discord.
- [x] 🌍 **Global Charts:** Daily updated charts from installed plugins.
- [x] 🖥️ **Cross-Platform:** Windows, Linux, Android, and macOS.
- [x] 💾 **Backup & Restore:** Export/import your library via JSON or M3U.
- [x] 🤖 **AI Recommendations:** Smarter song suggestions via Last.fm and plugins.
- [x] 🆎 **Multi-Language:** Localized for English, Hindi, Korean, German, Spanish, Japanese, Chinese.

---

## 🌍 Language Support

| Language | Native Name | Status |
|----------|------------|--------|
| 🇺🇸 English | English | ✅ Complete |
| 🇮🇳 Hindi | हिन्दी | ✅ Complete |
| 🇰🇷 Korean | 한국어 | ✅ Complete |
| 🇩🇪 German | Deutsch | ✅ Complete |
| 🇪🇸 Spanish | Español | ✅ Complete |
| 🇯🇵 Japanese | 日本語 | ✅ Complete |
| 🇨🇳 Chinese | 中文 | ✅ Complete |

---

## 📥 Download

<p align="center">
  <a href="https://github.com/ncntech/NasBeat/releases/latest">
    <img src="https://img.shields.io/badge/GitHub%20Releases-Download%20NasBeat-181717?style=for-the-badge&logo=github" alt="Download on GitHub" />
  </a>
</p>

| Platform | File |
|----------|------|
| 🤖 Android | `nasbeat_android_*.apk` |
| 🪟 Windows | `nasbeat_windows_x64_*.zip` |
| 🐧 Linux | `nasbeat_linux_x64_*.tar.gz` |
| 🍎 macOS | `nasbeat_macos_universal_*.zip` |

### Android
1. Download the APK from [GitHub Releases](https://github.com/ncntech/NasBeat/releases/latest).
2. Enable **Install unknown apps** in device settings.
3. Tap the APK and follow the prompts.

### Windows
1. Download and extract the `.zip`.
2. Run `nasbeat.exe` — no installer needed.

### Linux
```bash
tar -xzf nasbeat_linux_x64.tar.gz
./nasbeat
```

---

## 🔧 Build from Source

**Requirements:** Flutter 3.35.4 stable · Rust stable toolchain

```bash
git clone https://github.com/ncntech/NasBeat.git
cd NasBeat
flutter pub get
flutter run
```

---

## 🤝 Contributing

Pull requests are welcome. Please open an issue first to discuss what you'd like to change.

---

## 📄 License

[GNU GPL v3](LICENSE) — free and open source forever.

---

<div align="center">

Built with ❤️ by [NasTech](https://github.com/ncntech)

</div>
