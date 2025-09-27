# AUTOBLIND v1.0
**Smart Blinds Controller with WiFi Connectivity**

A WiFi-enabled smart blinds controller using ESP8266 and stepper motor control, with web interface and HTTP API for remote operation.

## Hardware Requirements

- **Wemos D1 Mini Pro** (ESP8266)
- **28BYJ-48 Stepper Motor** (5V)
- **ULN2003 Driver Board**
- **5V Power Supply** (min 1A)

### Wiring
| D1 Mini Pin | ULN2003 Pin |
|-------------|-------------|
| D1 | IN1 |
| D3 | IN2 |
| D4 | IN3 |
| D5 | IN4 |
| 5V | VCC |
| GND | GND |

## Features

- **50 Revolution Capacity**: 204,800 steps total range
- **WiFi Control**: Web interface + HTTP API
- **Position Memory**: Automatic saving/restoration
- **Reverse Direction**: Configurable for different installations
- **Safety**: Watchdog timer protection
- **Calibration**: Custom upper/lower limits

## Quick Start

1. **Flash firmware** to Wemos D1 Mini Pro
2. **Connect to WiFi**: Join "AUTOBLIND-Setup" (password: 12345678)
3. **Configure**: Open browser to `192.168.4.1`, set WiFi credentials
4. **Calibrate**: Set upper/lower positions via web interface

## Web Interface

- **Main**: `http://[IP]/` - Status and basic controls
- **Config**: `http://[IP]/config` - Motor settings and calibration
- **WiFi**: `http://[IP]/wifi` - Network configuration

## HTTP API

### Basic Control
```bash
# Move up/down
POST /api/move
Body: direction=up|down

# Stop motor
POST /api/stop

# Get status
GET /api/status
```

### Advanced Control
```bash
# Move specific steps
POST /api/move
Body: steps=1000

# Move to position
POST /api/move  
Body: position=-50000

# Set limits
POST /api/set_position
Body: type=upper|lower

# Reverse direction
POST /api/set_reverse
Body: reverse=true|false
```

### Browser URLs (for automation)
- `http://[IP]/api/move/direction=up`
- `http://[IP]/api/move/direction=down`
- `http://[IP]/api/stop`

## Configuration

### Motor Direction
If blinds move in wrong direction, enable reverse mode in web interface or via API.

### Position Limits
1. Move blinds to desired upper position
2. Save as upper limit
3. Move to desired lower position  
4. Save as lower limit

### WiFi Reset
Use web interface or API to clear WiFi settings and return to setup mode.

## Technical Specs

- **Range**: 0 to -204,800 steps (50 revolutions)
- **Resolution**: 4,096 steps per revolution
- **Speed**: 500 steps/second (conservative)
- **WiFi**: 2.4GHz 802.11 b/g/n
- **Power**: 5V DC, ~800mA peak

## Troubleshooting

- **Motor not moving**: Check 5V power supply and wiring
- **WiFi issues**: Reset WiFi config, check 2.4GHz network
- **Web interface**: Check IP address in serial console (115200 baud)
- **Wrong direction**: Enable reverse mode in configuration

## License

Copyright (C) 2025 Anders Isaksson. All rights reserved.
