# 🔐 Desktop Authenticator

A privacy-first, offline-capable **Google Authenticator (TOTP)** web application for desktop. Generate, manage, and copy your 2FA codes without needing your phone.

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Status: Offline](https://img.shields.io/badge/Offline-100%25-green.svg)

---

## ✨ Features

- **📷 QR Code Scanner & Image Upload:**
  - Drag and drop any 2FA QR code screenshot (`.png`, `.jpg`, `.webp`).
  - **Clipboard Paste (`Ctrl + V`):** Snip a QR code with `Win + Shift + S` and press `Ctrl + V` anywhere on the app to scan automatically!
  - **Google Authenticator Bulk Import:** Automatically decodes `otpauth-migration://` export QR codes and imports all accounts in one click.
- **⌨️ Manual Key Entry:** Add accounts using standard Base32 secret keys or `otpauth://` URIs.
- **⏱️ Live Synchronized Timer:** Real-time 30-second progress ring with urgency color alert when `< 5s` remain.
- **📋 1-Click Clipboard Copy:** Click any 6-digit code to copy directly to clipboard.
- **🔍 Instant Search & Filter:** Quickly filter through dozens of accounts by name or issuer.
- **🔒 100% Client-Side & Private:**
  - Standard RFC 6238 TOTP computation using native WebCrypto and pure JS SHA-1.
  - Zero external tracking or network requests.
  - Secrets are stored exclusively in your local browser `localStorage`.
- **📦 Backup & Restore:** Export and import your accounts as JSON anytime.

---

## 🚀 Quick Start

No build step or server required!

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/desktop-authenticator.git
   ```
2. Double-click `index.html` to open it in your browser (Chrome, Edge, Firefox, Safari).
3. (Optional) Create a desktop shortcut pointing to `index.html` to launch it directly from your desktop.

---

## 🛠️ How It Works

Google Authenticator uses the **TOTP algorithm (RFC 6238)**:
1. It takes the **Base32 Secret Key** shared between you and the service.
2. It divides current Unix time by 30 seconds to calculate the 30-second time slice.
3. It generates an **HMAC-SHA1** hash of the counter using the secret key.
4. It performs dynamic truncation to extract a 6-digit code.

Because this algorithm is deterministic based purely on time, this desktop app produces the **exact same code at the exact same second** as your mobile authenticator app.

---

## 🛡️ Security Best Practices

- Your secrets never leave your device.
- Keep your PC locked when unattended.
- Use the **Backup** button to keep a secure offline JSON backup of your accounts.

---

## 📄 License

MIT License. Free for personal and commercial use.
