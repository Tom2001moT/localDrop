# LocalDrop 📡

**Instant, encrypted, cross-platform file sharing between iPhone, Android, Mac, and Windows — directly in your browser.**

LocalDrop is an AirDrop-inspired peer-to-peer (P2P) file transfer web application built as a zero-backend, single-file static site. Files stream directly between devices over **DTLS-encrypted WebRTC DataChannels** without ever being uploaded to a cloud server.

---

## ✨ Key Features

- **🌐 True Cross-Platform Compatibility:** Works seamlessly across iOS (Safari), Android (Chrome), macOS, Windows, and Linux with zero app installation required.
- **📡 Automatic Same-Wi-Fi Radar:** Devices connected to the same Wi-Fi network automatically discover each other on an interactive radar using privacy-preserving SHA-256 public IP grouping.
- **📱 QR Code & 6-Digit Room Pairing:** Pair devices across cellular data (5G/LTE), personal hotspots, or separate networks by scanning a QR code with your phone's camera or entering a 6-digit room code.
- **🏷️ NFC Sticker Tap-to-Pair Support:** Write a static room link (`https://<username>.github.io/localdrop/?room=DESK01`) to any NTAG213 NFC tag so tapping either an iPhone or Android phone launches both devices straight into the same paired room.
- **🔒 End-to-End Encrypted & SHA-256 Verified:** Every transfer is encrypted via WebRTC DTLS and verified chunk-by-chunk using a streaming **Web Crypto SHA-256** rolling checksum.
- **⚡ High-Speed Flow-Controlled Streaming:** Streams multi-file batches in 64 KB chunks with a 2 MB sliding credit window, direct-to-disk saving on desktop browsers (File System Access API), live MB/s speedometer, and ETA countdown.
- **🖥️ Desktop Power-User Shortcuts:** Supports full-window drag-and-drop (including nested folders) and `Ctrl+V` / `Cmd+V` clipboard pasting for screenshots and files.
- **🔆 Mobile-First Polish:** Includes Screen Wake Lock support to prevent mobile displays from sleeping mid-transfer, Web Audio sound effects, and Home Screen PWA support.

---

## 🚀 Quick Start & Hosting on GitHub Pages

Because LocalDrop uses serverless WebRTC signaling over secure WebSockets (`wss://`), it requires **no backend server** and can be hosted for free on GitHub Pages:

1. Fork or upload `index.html` to the root of a public GitHub repository.
2. Open your repository **Settings → Pages**.
3. Under **Build and deployment → Source**, select **Deploy from a branch**, pick `main` and `/ (root)`, then click **Save**.
4. Access your live HTTPS app at `https://<your-username>.github.io/<repo-name>/`.

---

## 📲 How to Use

### On Same Wi-Fi
1. Open your LocalDrop URL on both devices (e.g., iPhone and Android).
2. Both devices will automatically appear on the radar.
3. Tap the recipient's device icon, select one or more files, and tap **Accept & Save** on the receiving device.

### On Cellular Data or Personal Hotspot
1. Open LocalDrop on the first device to display its **QR Code** and **6-digit Room Code**.
2. Point the second phone's built-in **Camera** at the QR code and tap the link (or enter the 6-digit code manually).

### Install as a Home Screen App
- **iPhone (Safari):** Tap **Share** → **Add to Home Screen**.
- **Android (Chrome):** Tap **⋮** → **Install app** (or **Add to Home screen**).

---

## 🛠️ Tech Stack

- **Transport & Security:** WebRTC (`RTCDataChannel`), DTLS encryption, Web Crypto API (`SHA-256`)
- **Discovery & Signaling:** Serverless MQTT over WSS + IPv4 SHA-256 group hashing
- **Storage & Hardware APIs:** File System Access API, Screen Wake Lock API, Web Audio API
- **UI & Styling:** Mobile-first Tailwind CSS, `qrcode.js`

---

## 📄 License

MIT License — free to use, modify, and self-host.