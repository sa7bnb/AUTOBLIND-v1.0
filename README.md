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

# Status (JSON)
http://[IP]/api/status
Advanced Control (POST)
bash# Move specific steps
POST /api/move
Body: steps=1000

# Move by revolutions
POST /api/move
Body: revolutions=5

# Absolute position
POST /api/move
Body: position=-50000

# Set limits
POST /api/set_position
Body: type=upper|lower

# Reverse direction
POST /api/set_reverse
Body: reverse=true|false
Example: Home Assistant Integration
yamlrest_command:
  blinds_up:
    url: "http://[IP]/api/move"
    method: POST
    payload: "direction=up"
  
  blinds_down:
    url: "http://[IP]/api/move"
    method: POST
    payload: "direction=down"

📊 Technical Specifications
ParameterValuePosition Range0 to -204,800 stepsRevolution Capacity50 full rotationsStep Resolution4,096 steps/revolutionMax Speed500 steps/secondWiFi2.4GHz 802.11 b/g/nPower Consumption~800mA peak

🔧 Troubleshooting
Motor Issues

❌ Not moving? → Check 5V power supply and wiring
🔄 Wrong direction? → Enable reverse mode in /config
⚡ Stops unexpectedly? → Verify power supply is 1A minimum

WiFi Issues

📶 Can't connect? → Ensure 2.4GHz network (5GHz not supported)
🔍 Lost connection? → Auto-retry every 30 seconds
📍 Find IP address? → Check Serial Monitor (115200 baud)

Web Interface

🌐 Can't access pages? → Verify device IP in Serial Monitor
🐌 Slow response? → Normal for ESP8266 during motor movement


📸 Screenshots
<div align="center">
Mobile Remote Interface
Clean 3-button control optimized for smartphones
Configuration Panel
Easy calibration and manual controls
Status Dashboard
Real-time monitoring with API reference
</div>

📝 Version Control
Current version uses EEPROM version tracking:

To force EEPROM reset: Increment VERSION_NUMBER in code
To preserve settings: Keep VERSION_NUMBER unchanged


📄 License
Copyright © 2025 Anders Isaksson. All rights reserved.

🤝 Contributing
This is a personal project. Feel free to fork and modify for your own use.

⚙️ Built With

ESP8266WiFi - WiFi connectivity
ESP8266WebServer - Web interface
AccelStepper - Motor control
EEPROM - Settings storage


<div align="center">
Made with ❤️ by Anders Isaksson
⬆ Back to Top
</div>
```
Denna layout innehåller:

Professionell header med badges
Tydlig innehållsförteckning
Visuellt separerade sektioner
Tabeller för bättre struktur
Ikoner för enklare navigation
Centrerad och balanserad design
GitHub-standard markdown
Responsiv layout som fungerar på både desktop och mobil
