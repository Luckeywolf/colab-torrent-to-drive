# 🚀 Colab Cloud Download Station (Ultimate Edition)

An enterprise-grade, high-throughput BitTorrent and Magnet link cloud downloader for Google Drive powered by Google Colab, Aria2, and P7Zip.

<p align="center">
  <a href="https://colab.research.google.com/github/Luckeywolf/colab-torrent-to-drive/blob/main/Torrent_To_Google_Drive.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab" height="38">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Colab">
  <img src="https://img.shields.io/badge/Aria2-Engine-blue?style=for-the-badge" alt="Aria2">
  <img src="https://img.shields.io/badge/P7Zip-Integrated-orange?style=for-the-badge" alt="P7Zip">
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License">
</p>

---

## ✨ Features

- **📥 Multi-Torrent Batch Queue:** Queue multiple magnet links, `.torrent` URLs, or multi-file uploads. Processes each job sequentially without manual intervention.
- **⏱️ Live Telemetry Dashboard:** Monospace instrumentation tracking transfer rates (`RATE`), byte progress (`TRANSFERRED / TOTAL`), active nodes (`PEERS`), live `ELAPSED` timer, and remaining `ETA`.
- **📦 Auto-Archive Extraction:** Automatically detects and unpacks compressed scene releases (`.rar`, `.zip`, `.7z`, multi-volume `.r01`) on Colab's high-speed local disk before syncing to Drive, cleaning up raw archive chunks to save cloud storage.
- **🛡️ 100% Corruption-Free Sync:** Uses a safe two-stage pipeline (buffers to local NVMe SSD first, then streams sequentially via a 16 MB memory buffer into Google Drive with `os.sync()`). Completely eliminates Drive FUSE chunk truncation.
- **💾 Google Drive Pre-Flight Check:** Instantly displays available Google Drive storage at startup to prevent running out of cloud disk space mid-download.
- **🚀 Live Tier-1 Public Trackers:** Queries 20+ verified high-speed BitTorrent trackers dynamically on launch for instant swarm saturation (up to 50–100+ MB/s).
- **🔔 Discord / Telegram Webhook Alerts:** Optionally enter a webhook URL to receive an instant alert on your phone/desktop the moment your downloads are verified and resting in Google Drive.
- **⚡ Hardware-Tuned Engine:** Pre-configured with 64 MB RAM disk caching, 128 concurrent peers, and instant `falloc` file allocation.

---

## 🚀 Quick Start (1-Click Run)

1. Click the **[Open In Colab](https://colab.research.google.com/github/Luckeywolf/colab-torrent-to-drive/blob/main/Torrent_To_Google_Drive.ipynb)** button above.
2. Click the **Play (▶)** button on the downloader cell.
3. Authorize Google Drive access when prompted.
4. Input your targets:
   - **Magnet Links / URLs:** Paste one or multiple links (one per line, type `done` or press Enter on an empty line when finished).
   - **Local `.torrent` Files:** Leave empty and press Enter to upload files from your device.
5. *(Optional)* Paste a Discord webhook URL to receive notifications when complete, or press Enter to skip.
6. The dashboard will track live transfer speed, elapsed time, and ETA. Once completed, your files will be verified and waiting in `Google Drive > My Drive > Torrent`!

---

## 📋 Architecture & Comparison

| Capability | Legacy Libtorrent Notebooks | Colab Cloud Download Station |
| :--- | :--- | :--- |
| **File Integrity** | ❌ Direct random writes crash Drive FUSE (files truncate to ~1.7 GB) | ✅ **Safe 2-Stage Pipeline:** Local NVMe buffer + 16 MB sequential stream + `os.sync()` flush |
| **Batch Queuing** | ❌ Single download per cell run | ✅ **Multi-Target Queue:** Batch process multiple links or files |
| **Compressed Media** | ❌ Uploads raw useless `.rar` archives | 📦 **Auto-Extraction:** Automatically unpacks `.rar`/`.zip` and saves clean media |
| **Seeder Discovery** | ⚠️ Relies only on magnet trackers (10–20 MB/s) | ⚡ **Live Tier-1 Trackers:** Queries 20+ top public trackers on startup (50–100+ MB/s) |
| **Monitoring** | ⚠️ Choppy text logs or broken sliders | 📊 **Minimal Monospace Telemetry:** Live rate, elapsed clock, ETA, peers, and avg throughput |
| **Drive Awareness** | ❌ Fails without warning if Drive is full | 💾 **Pre-Flight Storage Meter:** Checks remaining Google Drive space before downloading |
| **Notifications** | ❌ None | 🔔 **Webhook Integration:** Discord/Telegram alerts upon completion |

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
