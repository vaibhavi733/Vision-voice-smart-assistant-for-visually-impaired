# 🦯 Vision Voice: Smart Assistant for Visually Impaired



  A multi-functional AI-powered mobile and web application designed to enhance the independence, mobility, and safety of visually impaired individuals.


---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Features](#features)
- [System Architecture](#system-architecture)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Future Scope](#future-scope)
- [Team](#team)
- [Acknowledgements](#acknowledgements)

---

## 📖 About the Project

**Vision Voice** is an innovative assistive technology solution aimed at empowering visually impaired individuals with greater independence in their daily lives. According to the WHO, approximately **2.2 billion people** globally experience some form of vision impairment. This project bridges the gap using AI, computer vision, and voice technologies.

The application combines:
- **Indoor Navigation** via QR code scanning
- **Outdoor Navigation** powered by Google Maps and voice commands
- **Real-Time Object Detection** using YOLOv8
- **Emergency SOS Alerts** with live GPS location sharing
- **Product Identification** via barcode scanning



---

## ✨ Features

### 🏠 Indoor Navigation
Scan QR codes placed on room doors or walls to instantly receive spoken room details via Text-to-Speech (TTS). Navigate complex indoor spaces like hospitals, malls, and offices completely hands-free.

### 🗺️ Outdoor Navigation
Speak your destination and let the app handle the rest. Powered by Google Maps API and Google Speech-to-Text, it provides continuous turn-by-turn voice guidance with real-time GPS tracking.

### 🚨 SOS Emergency Alert
Press a single button to instantly send your live GPS location and a distress message to pre-registered emergency contacts via SMS — no typing required.

### 👁️ Object Detection
A YOLOv8-powered web module streams your camera feed and detects nearby objects in real time. Detected objects are announced aloud with spatial cues (e.g., *"Chair on the left"*) to help avoid obstacles.

### 🛒 Barcode Scanner
Scan any product barcode in a supermarket to retrieve its name, price, and description from a product database — all read aloud via TTS for a fully autonomous shopping experience.

---

## 🏗️ System Architecture

```
Vision-Voice Core System (Central Controller)
│
├── Object Detection Module
│   ├── OpenCV Camera Integration
│   └── YOLO Object Detection
│
├── Emergency SOS Module
│   ├── Location Services → Google Maps API
│   └── Emergency Contact System → SMS/Messaging Service
│
├── Outdoor Navigation Module
│   ├── Voice Input Processing → Speech-to-Text Engine
│   └── Maps Navigation Integration → Text-to-Speech Engine
│
├── Indoor Navigation Module
│   ├── QR Code Scanner
│   └── Room Information System → Room Information Database
│
└── Product Scanner Module
    ├── Barcode Scanner
    └── Product Information System → Product Information Database
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Mobile App | Java, Android SDK, Android Studio |
| Web Backend | Python, Flask, Flask-CORS |
| Object Detection | YOLOv8, OpenCV |
| Navigation | Google Maps API, Google Places API |
| Voice | Google TTS, Google Speech-to-Text API |
| QR / Barcode Scanning | ML Kit, ZXing (Zebra Crossing) |
| Database | SQLite / MySQL, SQLAlchemy |
| Version Control | Git, GitHub |

---

## 🚀 Getting Started

### Prerequisites

**For the Android App:**
- Android Studio (latest stable)
- JDK 8 or higher
- Android device running Android 7.0 (Nougat) or higher
- Google Maps API key

**For the Flask Web App (Object Detection):**
- Python 3.7+
- pip

### Installation

#### 1. Clone the Repository

```bash
git clone https://github.com/vaibhavi733/vision-voice.git
cd vision-voice
```

#### 2. Android App Setup

1. Open the `android-app/` folder in **Android Studio**.
2. Add your Google Maps API key in `AndroidManifest.xml`:
   ```xml
   <meta-data
       android:name="com.google.android.geo.API_KEY"
       android:value="YOUR_API_KEY_HERE" />
   ```
3. Build and run the app on your device or emulator.

#### 3. Flask Web App Setup (Object Detection)

```bash
cd web-app
pip install -r requirements.txt
```

Download YOLOv8 weights:
```bash
# yolov8n.pt will be auto-downloaded on first run via ultralytics
```

Update the IP Webcam stream URL in `web-app.py`:
```python
VIDEO_URL = 'http://<your-phone-ip>:8080/video'
```

Run the server:
```bash
python web-app.py
```



---

## 📱 Usage

| Feature | How to Use |
|---|---|
| **Indoor Navigation** | Tap "Indoor Navigation" → Point camera at a QR code → Hear room details aloud |
| **Outdoor Navigation** | Tap "Outdoor Navigation" → Tap "Start Navigation" → Speak your destination → Follow voice directions |
| **SOS Alert** | Tap "SOS Alert" → Your GPS location is sent via SMS to your emergency contact instantly |
| **Object Detection** | Open the web app on a browser → Point your camera → Hear nearby objects announced in real time |
| **Product Scanner** | Tap "Scanner" → Point camera at a product barcode → Hear the product name and details |

---

## 📁 Project Structure

```
vision-voice/
│
├── android-app/                  # Android mobile application (Java)
│   ├── app/src/main/java/
│   │   ├── MainActivity.java         # Navigation launcher
│   │   ├── SOSAlertActivity.java     # SOS emergency feature
│   │   └── QRCodeScannerActivity.java # Indoor navigation
│   └── app/src/main/res/
│       └── layout/                   # UI layouts
│
├── web-app/                      # Flask web application (Python)
│   ├── web-app.py                    # Main Flask server with YOLO integration
│   └── templates/
│       └── index.html                # Web UI for object detection
│
├── docs/                         # Project report and documentation
│
└── README.md
```

---



## 🔮 Future Scope

- **Enhanced Object Detection** — Recognize a broader range of objects with distance estimation and real-time hazard alerts
- **Bluetooth Beacon Indoor Navigation** — Replace QR codes with BLE beacons or indoor positioning systems (IPS) for seamless indoor guidance
- **Augmented Reality (AR) Navigation** — Overlay visual/vibrational cues for more intuitive outdoor navigation
- **Expanded Language Support** — Add support for regional Indian languages and dialects
- **Voice-Integrated Online Shopping** — Connect barcode scanning with e-commerce platforms for home shopping
- **Offline Mode** — Core navigation features available without internet connectivity

---



## 🙏 Acknowledgements

- [YOLOv8 by Ultralytics](https://github.com/ultralytics/ultralytics)
- [Google Maps Platform](https://developers.google.com/maps)
- [ZXing Barcode Scanning Library](https://github.com/zxing/zxing)
- [Google ML Kit](https://developers.google.com/ml-kit)
- [OpenCV](https://opencv.org/)
- [Flask](https://flask.palletsprojects.com/)
