# ⚡ Colab Torrent to Google Drive Downloader

A fast, lightweight, and reliable tool to download BitTorrent files and Magnet links directly into your Google Drive using Google Colab.

<p align="center">
  <a href="https://colab.research.google.com/github/Luckeywolf/colab-torrent-to-drive/blob/main/Torrent_To_Google_Drive.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab" height="36">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Colab">
  <img src="https://img.shields.io/badge/Aria2-Powered-blue?style=for-the-badge" alt="Aria2">
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License">
</p>

---

## ✨ Features

- **🚀 Ultra-Fast Speeds:** Utilizes Aria2's multi-connection engine to maximize Google Colab's high-bandwidth network (up to 50–100+ MB/s).
- **🛡️ 100% Reliable:** Replaces outdated `libtorrent` packages that constantly break on modern Colab runtime updates.
- **📁 Direct Google Drive Sync:** Downloads are saved straight to `Google Drive > My Drive > Torrent`.
- **🔗 Universal Input:** Accepts Magnet links, `.torrent` HTTP/HTTPS URLs, or direct file uploads from your local computer.
- **🖥️ Zero Setup:** Runs entirely inside your browser. No local software installation needed.

---

## 🚀 Quick Start (1-Click Run)

1. Click the **[Open In Colab](https://colab.research.google.com/github/Luckeywolf/colab-torrent-to-drive/blob/main/Torrent_To_Google_Drive.ipynb)** button above.
2. Click the **Play (▶)** button on the downloader cell.
3. When prompted, authorize **Google Drive** access.
4. Paste your **Magnet link** or `.torrent` URL (or press Enter without typing anything to upload a `.torrent` file from your computer).
5. Watch the download progress in real-time. Once completed, your files will be waiting in your Google Drive under `/Torrent`!

---

## 📋 Comparison

| Feature | Legacy Libtorrent Notebooks | This Project (Aria2 Engine) |
| :--- | :--- | :--- |
| **Compatibility** | ❌ Breaks on Ubuntu 22.04+ runtimes | ✅ Always compatible |
| **Download Speeds** | ⚠️ Moderate (single/limited sockets) | ⚡ Multi-connection saturation (16 connections/server) |
| **Google Drive I/O** | ❌ Frequent FUSE lockups & freezes | ✅ Smooth chunk streaming |
| **Input Options** | ⚠️ Clunky multi-cell interface | ✅ Unified (Magnet, URL, or File Upload) |

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
