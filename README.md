<div align="center">

# 🪟 AUTOBLIND v1.0

**WiFi Smart Blinds Controller**

[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-ESP8266-blue.svg)](https://www.espressif.com/)
[![Version](https://img.shields.io/badge/Version-1.0-green.svg)]()

*Control your blinds from anywhere with a mobile-friendly interface and automation-ready API*

[Features](#features) • [Hardware](#hardware) • [Setup](#quick-setup) • [API](#api) • [Troubleshooting](#troubleshooting)

</div>

---

## 📋 Features

- 📱 **Mobile Remote** - Touch-optimized 3-button interface
- 🌐 **Web Dashboard** - Real-time status monitoring
- 🔧 **Easy Calibration** - Set custom upper/lower limits
- 🔄 **Reverse Direction** - Works with any installation
- 💾 **Position Memory** - Survives power loss
- 🚀 **HTTP API** - Full automation support
- 📏 **50 Revolution Range** - 204,800 steps capacity

---

## 🛠 Hardware

| Component | Description |
|-----------|-------------|
| **Microcontroller** | Wemos D1 Mini Pro (ESP8266) |
| **Motor** | 28BYJ-48 Stepper Motor (5V) |
| **Driver** | ULN2003 Driver Board |
| **Power** | 5V 1A Power Supply |

### Wiring Diagram
D1 Mini Pin  →  ULN2003 Pin
─────────────────────────────
D1           →  IN1
D3           →  IN2
D4           →  IN3
D5           →  IN4
5V           →  VCC
GND          →  GND

---

## 🚀 Quick Setup

1. **Flash Firmware**
   - Upload code to Wemos D1 Mini Pro using Arduino IDE

2. **Initial Configuration**
   - Connect to WiFi: `AUTOBLIND-Setup` (password: `12345678`)
   - Browse to `192.168.4.1`
   - Enter your home WiFi credentials

3. **Calibration**
   - Navigate to `/config`
   - Move blinds to fully open position → Click "Save as UPPER"
   - Move blinds to fully closed position → Click "Save as LOWER"

4. **Ready to Use!**
   - Access mobile remote at `http://[YOUR-IP]/remote`

---

## 🌐 Web Interface

| Page | URL | Description |
|------|-----|-------------|
| **Dashboard** | `/` | Status cards & API reference |
| **Remote** | `/remote` | Mobile control interface |
| **Config** | `/config` | Motor settings & calibration |
| **WiFi** | `/wifi` | Network configuration |

---

## 🔌 API

### Browser URLs (Simple GET)
```bash
# Move up
http://[IP]/api/move/direction=up

# Move down
http://[IP]/api/move/direction=down

# Stop
http://[IP]/api/stop

🔧 Troubleshooting
Motor Issues

❌ Not moving? → Check 5V power supply and wiring
🔄 Wrong direction? → Enable reverse mode in /config
⚡ Stops unexpectedly? → Verify power supply is 1A minimum

WiFi Issues

📶 Can't connect? → Ensure 2.4GHz network (5GHz not supported)
🔍 Lost connection? → Auto-retry every 30 seconds
📍 Find IP address? → Check Serial Monitor (115200 baud)

📄 License
Copyright © 2025 Anders Isaksson. All rights reserved.

⚙️ Built With

ESP8266WiFi - WiFi connectivity
ESP8266WebServer - Web interface
AccelStepper - Motor control
EEPROM - Settings storage
