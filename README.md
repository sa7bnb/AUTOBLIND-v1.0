🏠 AUTOBLIND v1.0
Smart Motorized Blind Controller with WiFi & Scheduling
Automated blind control system with web interface and intelligent scheduling
</div>

✨ Key Features
🌐 WiFi Control
Control blinds via web browser from any device on your home network
⏰ Smart Scheduling
Automatic up/down control based on weekly schedule with NTP time synchronization
🎯 Precision Calibration
Adjustable upper and lower position limits for exact control
⚡ Energy Efficient
Motor coils automatically released after movement to minimize heat generation
📱 Responsive Interface
Mobile-optimized web interface with real-time status updates
🔧 Easy Setup
Access Point mode for simple initial configuration without external router

🔧 Hardware Requirements
ComponentSpecificationMicrocontrollerWemos D1 Mini Pro (ESP8266)Motor28BYJ-48 Stepper MotorDriverULN2003 Motor DriverCapacity50 revolutions (204,800 steps)

🚀 API Endpoints
Simple HTTP-based control for home automation integration:
httpPOST /api/move?direction=up/down    # Move blinds
GET  /api/status                     # Get current status
POST /api/set_schedule               # Configure schedule

📄 License
Copyright © 2025 A. Isaksson. All rights reserved.

<div align="center">
Made with ❤️ for smart home automation
</div>
