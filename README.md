<div align="center">

<br/>

```ruby
███████╗██╗      █████╗ ███████╗██╗  ██╗███████╗ ██████╗ ██████╗  ██████╗ ███████╗
██╔════╝██║     ██╔══██╗██╔════╝██║  ██║██╔════╝██╔═══██╗██╔══██╗██╔════╝ ██╔════╝
█████╗  ██║     ███████║███████╗███████║█████╗  ██║   ██║██████╔╝██║  ███╗█████╗  
██╔══╝  ██║     ██╔══██║╚════██║██╔══██║██╔══╝  ██║   ██║██╔══██╗██║   ██║██╔══╝  
██║     ███████╗██║  ██║███████║██║  ██║██║     ╚██████╔╝██║  ██║╚██████╔╝███████╗
╚═╝     ╚══════╝╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝╚═╝      ╚═════╝ ╚═╝  ╚═╝ ╚═════╝ ╚══════╝
```

### ⚡ Browser-based ESP32 / ESP8266 Firmware Flasher

<br/>

![GitHub stars](https://img.shields.io/github/stars/rsnithesh/FlashForge?style=for-the-badge&color=a855f7&labelColor=0f0a1e)
![GitHub forks](https://img.shields.io/github/forks/rsnithesh/FlashForge?style=for-the-badge&color=c084fc&labelColor=0f0a1e)
![GitHub issues](https://img.shields.io/github/issues/rsnithesh/FlashForge?style=for-the-badge&color=9333ea&labelColor=0f0a1e)
![License](https://img.shields.io/github/license/rsnithesh/FlashForge?style=for-the-badge&color=7c3aed&labelColor=0f0a1e)

<br/>

**Flash firmware to any ESP32 or ESP8266 board — directly from your browser.**  
No drivers. No software. No hassle.

<br/>

[🚀 **Launch App**](https://R-S-Nithesh.github.io/FlashForge) · [🐛 Report Bug](https://github.com/R-S-Nithesh/FlashForge/issues) · [💡 Request Feature](https://github.com/R-S-Nithesh/FlashForge/issues)

<br/>

</div>

---

## 📸 Preview

> A clean, dark-themed flasher UI with animated background, device info panel, serial console, and one-click flashing.

---

## ✨ Features

| Feature | Description |
|---|---|
| ⚡ **One-Click Flash** | Drop a `.bin` file and hit Flash — done |
| 🔌 **WebSerial** | Runs entirely in Chrome / Edge, zero installs |
| 📋 **Device Info** | Reads chip family, MAC address & flash size on connect |
| 🖥️ **Serial Console** | Live read + send commands over serial |
| 📁 **Drag & Drop** | Drop zone UI with progress bar for visual feedback |
| 🕒 **Flash History** | Recent flash records stored in your browser |
| 🌙 **Dark / Light** | Full theme toggle with smooth transitions |
| 💜 **Purple UI** | Animated particle background, glowing panels |

---

## 🛠️ Supported Boards

FlashForge works with any ESP32 or ESP8266 board that supports WebSerial:

- **ESP32** (all variants — S2, S3, C3, C6…)
- **ESP8266** (NodeMCU, Wemos D1 Mini, etc.)
- Any custom board based on the above chips

---

## 🚀 Getting Started

### Prerequisites

| Requirement | Details |
|---|---|
| **Browser** | Google Chrome or Microsoft Edge (v89+) |
| **Connection** | USB cable to your ESP board |
| **Firmware** | A compiled `.bin` file for your board |

> ⚠️ WebSerial is **not supported** in Firefox, Safari, or mobile browsers.

### Usage

```
1.  Open FlashForge in Chrome / Edge
2.  Click  [ Connect ]  and select your COM port
3.  Drag & drop your .bin file  (or click to browse)
4.  Hit  [ Flash ]
5.  Watch the progress bar — done in seconds ✅
```

That's it. No terminal, no Python, no esptool installation.

---

## 🏗️ How It Works

```
 ┌──────────────────────────────────────────────────┐
 │                   Your Browser                   │
 │                                                  │
 │   FlashForge UI  →  WebSerial API                │
 │                          │                       │
 │                    esptool-js (WASM)              │
 │                          │                       │
 └──────────────────────────┼───────────────────────┘
                            │  USB / Serial
                    ┌───────▼────────┐
                    │   ESP32 Board  │
                    └────────────────┘
```

FlashForge uses the **[WebSerial API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Serial_API)** to open a raw serial connection from the browser, and **[esptool-js](https://github.com/espressif/esptool-js)** (the official Espressif WASM port) to handle the ROM bootloader protocol, erasing, and writing flash sectors.

---

## 📁 Project Structure

```
FlashForge/
├── index.html          # Single-file app — all HTML, CSS & JS
└── README.md           # You are here
```

FlashForge is intentionally a **single HTML file** — no build step, no dependencies to install, no bundler. Open it locally or host it anywhere static.

---

## 🌐 Self-Hosting

Since it's one file, hosting is trivial:

**GitHub Pages**
```bash
# Push index.html to your repo, enable Pages → done
```

**Local**
```bash
# Just open in Chrome — no server needed for local .bin files
open index.html
```

**Any static host** — Netlify, Vercel, Cloudflare Pages, S3, etc.

> When hosted on HTTPS, WebSerial works over secure origins automatically.

---

## 🧩 Tech Stack

| Technology | Role |
|---|---|
| **WebSerial API** | Browser ↔ USB serial bridge |
| **esptool-js v0.4.5** | ESP ROM bootloader protocol |
| **Vanilla JS (ESM)** | No framework, no build step |
| **CSS Animations** | Particle canvas, gradient orbs, shimmer |
| **Outfit + JetBrains Mono** | Typography |

---

## 🤝 Contributing

Contributions are welcome! Here's how:

```bash
# 1. Fork the repo
# 2. Create your feature branch
git checkout -b feature/amazing-feature

# 3. Commit your changes
git commit -m "Add amazing feature"

# 4. Push and open a Pull Request
git push origin feature/amazing-feature
```

**Ways to contribute:**
- 🐛 Report bugs via [Issues](https://github.com/rsnithesh/FlashForge/issues)
- 💡 Suggest features or UI improvements
- 🌍 Help test on different boards and browsers
- ⭐ Star the repo if it helped you

---

## 📜 License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for details.

---

## 🙏 Acknowledgements

- [Espressif](https://github.com/espressif/esptool-js) — for esptool-js
- [WebSerial API](https://wicg.github.io/serial/) — W3C / WICG spec
- Original concept inspired by [FirmwareHub](https://github.com/cifertech/FirmwareHub) by CiferTech

---

<div align="center">

<br/>

Built with 💜 by **R.S.Nithesh** · Powered by WebSerial + esptool-js

<br/>

![Made with love](https://img.shields.io/badge/made%20with-💜-a855f7?style=for-the-badge&labelColor=0f0a1e)

</div>
