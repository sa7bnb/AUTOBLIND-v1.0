# 🏠 AUTOBLIND v1.1

**Smart Motorized Blind Controller with WiFi & Scheduling**

[![ESP8266](https://img.shields.io/badge/Platform-ESP8266-blue.svg)](https://www.espressif.com/)
[![License](https://img.shields.io/badge/License-Copyright-red.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Stable-green.svg)]()

*Automated blind control system with web interface and intelligent scheduling*

---

## ✨ Key Features

### 🌐 WiFi Control
Control blinds via web browser from any device on your home network

### ⏰ Smart Scheduling
Automatic up/down control based on weekly schedule with NTP time synchronization

### 🎯 Precision Calibration
Adjustable upper and lower position limits for exact control and speed settings.

### ⚡ Energy Efficient
Motor coils automatically released after movement to minimize heat generation

### 📱 Responsive Interface
Mobile-optimized web interface with real-time status updates

### 🔧 Easy Setup
Access Point mode for simple initial configuration without external router

---

## 🔧 Hardware Requirements

| Component | Specification |
|-----------|--------------|
| **Microcontroller** | Wemos D1 Mini Pro (ESP8266) |
| **Motor** | 28BYJ-48 Stepper Motor |
| **Driver** | ULN2003 Motor Driver |
| **Capacity** | 50 revolutions (204,800 steps) |

---

## 🚀 API Endpoints

Simple HTTP-based control for home automation integration:
```http
POST /api/move?direction=up/down    # Move blinds
GET  /api/status                     # Get current status
POST /api/set_schedule               # Configure schedule

📄 License
Copyright © 2025 A. Isaksson. All rights reserved.
