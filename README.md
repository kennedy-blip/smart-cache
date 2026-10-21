# 🚀 Local Media Automation & Smart Caching Gateway

> **Slash high mobile data tariffs and streaming subscription costs** by building an automated, off-peak media caching server for your workstation or local network.

---

## 🎯 Problem & Solution

### The Problem
Continuous streaming of videos, podcasts, and online courses over high-cost cellular data or metered connections quickly drains your data plan and incurs recurring bandwidth expenses.

### The Solution
The **Local Media Automation & Smart Caching Gateway** operates as an intelligent local media server. Instead of streaming content on demand during daytime hours, it uses automated background tasks to fetch queued YouTube videos, RSS podcast feeds, and educational content during **off-peak hours** (e.g., 12:00 AM – 6:00 AM) or when connected to free Wi-Fi. 

It automatically organizes, transcodes, and streams the media across your Local Area Network (LAN) to your TV, smartphone, or laptop—without consuming a single megabyte of mobile data during the day.

---

## ✨ Key Features

- ⚡ **Automated Off-Peak Caching:** Schedule downloads using `yt-dlp` and RSS feed watchers during free or discounted data windows.
- 📺 **Local LAN Streaming Server:** Stream high-quality videos and podcasts directly to TV/mobile browsers via FastAPI static file endpoints.
- 📊 **Real-time Cost & Data Analytics:** Track data savings in GB and local currency (e.g., KES / USD) alongside live disk usage breakdowns.
- ⚙️ **Smart Automation Rules:** Auto-transcode content to H.264/AAC for TV compatibility, restrict transfers to Wi-Fi only, and auto-purge watched media.
- 💻 **Interactive Control Dashboard:** A modern, single-page dashboard with active queue trackers, connected device monitors, and a built-in media preview player.

---

## 🏗️ System Architecture

```text
  ┌────────────────────────┐      ┌─────────────────────────┐
  │   Online Media Sources │      │    Off-Peak Scheduler   │
  │  (YouTube, RSS Feeds)  │      │   (12:00 AM - 6:00 AM)  │
  └───────────┬────────────┘      └────────────┬────────────┘
              │                                │
              ▼                                ▼
     ┌──────────────────────────────────────────────────┐
     │      Python / FastAPI Caching Gateway Node       │
     │   - yt-dlp Fetch Engine                          │
     │   - FFmpeg Auto-Transcoder                       │
     │   - Media Library & Local HTTP Server            │
     └────────────────────────┬─────────────────────────┘
                              │
                    Local Area Network (LAN)
                              │
     ┌────────────────────────┼────────────────────────┐
     ▼                        ▼                        ▼
┌──────────────┐      ┌──────────────┐      ┌──────────────┐
│  Smart TV    │      │  Smartphones │      │   Laptops    │
└──────────────┘      └──────────────┘      └──────────────┘
```

---

## 💻 Tech Stack

- **Dashboard UI:** HTML5, Tailwind CSS, Lucide Icons, Chart.js
- **Backend Framework:** FastAPI (Python)
- **Engine & Processing:** `yt-dlp`, FFmpeg, Asyncio background tasks

---

## 🚀 Quick Start Guide

### 1. Prerequisites
Ensure you have Python 3.10+ and `ffmpeg` installed on your machine:
```bash
# Ubuntu/Debian
sudo apt update && sudo apt install python3 ffmpeg -y

# macOS
brew install python ffmpeg
```

### 2. Installation
Clone the repository and install the required Python dependencies:
```bash
git clone https://github.com/your-username/streamcache-gateway.git
cd streamcache-gateway

pip install fastapi uvicorn yt-dlp
```

### 3. Running the Gateway
Launch the FastAPI server:
```bash
uvicorn main_gateway:app --host 0.0.0.0 --port 8000 --reload
```

Open your browser and navigate to:
- **Dashboard Interface:** `http://localhost:8000` (or `http://<YOUR-LAN-IP>:8000` from mobile/TV)
- **API Documentation:** `http://localhost:8000/docs`

---

## 📄 License

This project is licensed under the MIT License. Feel free to modify and expand it for personal or community setups!