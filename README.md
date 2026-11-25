# ⚡ Colab Torrent to Google Drive Downloader

A high-speed, reliable tool to download BitTorrent files and Magnet links directly into your Google Drive using Google Colab.

<p align="center">
  <a href="https://colab.research.google.com/github/Luckeywolf/colab-torrent-to-drive/blob/main/Torrent_To_Google_Drive.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab" height="36">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Colab">
  <img src="https://img.shields.io/badge/Aria2-Turbo-blue?style=for-the-badge" alt="Aria2">
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License">
</p>

---

## ✨ Key Features

- **🚀 Live Tier-1 Tracker Injection:** Queries and loads 20+ high-speed public trackers dynamically on launch, finding seeders up to 5× faster.
- **🛡️ 100% Corruption-Free Sync:** Uses a two-stage pipeline (buffers to local NVMe SSD first, then transfers sequentially via a 16 MB stream into Google Drive). Completely prevents Google Drive FUSE file truncation and unplayable files.
- **📊 Minimalist Technical Telemetry:** Real-time monospace dashboard displaying transfer rate (`RATE`), exact byte counters (`TRANSFERRED / TOTAL`), active nodes (`PEERS`), and remaining time (`ETA`).
- **⚡ Hardware-Tuned Engine:** Pre-configured with 64 MB RAM disk caching, 128 concurrent peers, and instant `falloc` file allocation.
- **🔗 Universal Input:** Supports Magnet links, `.torrent` HTTP/HTTPS URLs, and local `.torrent` file uploads.

---

## 🚀 Quick Start (1-Click Run)

1. Click the **[Open In Colab](https://colab.research.google.com/github/Luckeywolf/colab-torrent-to-drive/blob/main/Torrent_To_Google_Drive.ipynb)** button above.
2. Click the **Play (▶)** button on the downloader cell.
3. When prompted, authorize **Google Drive** access.
4. Paste your **Magnet link** or `.torrent` URL (or press Enter without typing anything to upload a `.torrent` file from your computer).
5. Monitor the live technical dashboard in real-time. Once complete, your verified files will be waiting in your Google Drive under `/Torrent`!

---

## 📋 Architecture & Comparison

| Feature | Legacy Libtorrent Notebooks | This Project (Turbo Aria2) |
| :--- | :--- | :--- |
| **Google Drive I/O** | ❌ Direct random chunk writes crash Drive FUSE (files truncate to ~1.7 GB) | ✅ **Safe 2-Stage Pipeline:** Local NVMe buffer + sequential 16 MB Drive stream with `os.sync()` |
| **Download Speeds** | ⚠️ Slow peer discovery (10–20 MB/s) | ⚡ **Up to 50–100+ MB/s** (20+ live Tier-1 trackers + 128 max peers) |
| **Disk Performance** | ⚠️ High disk write latency | 🚀 **64 MB RAM Cache** buffers data bursts before disk commit |
| **Interface** | ⚠️ Clunky multi-cell code | 📊 **Minimalist Technical Dashboard** with real-time rate & ETA |
| **Compatibility** | ❌ Broken C++ package bindings on modern Colab | ✅ **100% Native & Self-Contained** |

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
