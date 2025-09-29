AUTOBLIND v1.0
WiFi Smart Blinds Controller
Control your blinds from anywhere with a mobile-friendly interface and automation-ready API.
Hardware

Wemos D1 Mini Pro (ESP8266)
28BYJ-48 Stepper Motor + ULN2003 Driver
5V 1A Power Supply

Wiring
D1→IN1, D3→IN2, D4→IN3, D5→IN4, 5V→VCC, GND→GND
Features

Mobile Remote (/remote) - Three-button touch interface
Web Dashboard (/) - Status monitoring & API reference
Configuration (/config) - Calibration & manual controls
HTTP API - Full automation support
50 Revolution Range - 204,800 steps capacity
Position Memory - Survives power loss
Reverse Direction - Works with any installation

Quick Setup

Flash firmware to Wemos D1 Mini Pro
Connect to "AUTOBLIND-Setup" WiFi (password: 12345678)
Browse to 192.168.4.1 and configure your WiFi
Calibrate upper/lower positions in /config
Use /remote for daily control

API Examples
bash# Simple browser URLs
http://[IP]/api/move/direction=up
http://[IP]/api/move/direction=down
http://[IP]/api/stop

# POST for advanced control
POST /api/move
Body: steps=1000 | position=-50000 | revolutions=5
Troubleshooting

Wrong direction? Enable reverse in /config
Find IP address? Serial Monitor at 115200 baud
WiFi issues? Must be 2.4GHz network

Copyright © 2025 Anders Isaksson
