# 🌡️ ESP8266 DHT11 IoT Project — Temperature & Humidity Monitoring with KiwisIoT

![Platform](https://img.shields.io/badge/Board-ESP8266%20NodeMCU-blue)
![Sensor](https://img.shields.io/badge/Sensor-DHT11-green)
![IDE](https://img.shields.io/badge/IDE-Arduino-00979D)
![License](https://img.shields.io/badge/License-MIT-yellow)

Monitor **temperature** and **humidity** in real time using a **DHT11** sensor and an **ESP8266 NodeMCU**. The ESP8266 reads both values and sends them over Wi-Fi to a **KiwisIoT** dashboard, using two separate channels.

![KiwisIoT Dashboard](docs/images/kiwisiot-dashboard.jpg)

---

## 🚀 Project Highlights

- ESP8266-based temperature and humidity monitoring
- DHT11 digital sensor
- Real-time readings on a KiwisIoT dashboard
- Separate dashboard channels for temperature and humidity
- Handles invalid sensor readings
- Beginner-friendly — suitable for engineering and college IoT projects

## 📋 Project Overview

| Channel | Data        | Example |
|:-------:|-------------|:-------:|
| 0       | Temperature | 33.8 °C |
| 1       | Humidity    | 57.0 %  |

```
DHT11 Sensor → ESP8266 NodeMCU → Wi-Fi → KiwisIoT → IoT Dashboard
```

## 🔧 Components Required

| Component         | Quantity    |
|-------------------|-------------|
| ESP8266 NodeMCU   | 1           |
| DHT11 sensor module | 1         |
| Jumper wires      | As required |
| USB cable         | 1           |
| Computer          | 1           |

> The DHT11 **module** (3-pin board) already includes the pull-up resistor, so no external resistor is needed.

## 💻 Software Requirements

- Arduino IDE
- ESP8266 board package
- KiwisIoT Arduino library
- **DHT sensor library** (Adafruit)
- **Adafruit Unified Sensor** library
- KiwisIoT account + Wi-Fi connection

See [docs/SETUP.md](docs/SETUP.md) for step-by-step installation.

## 🔌 Circuit Connection

| DHT11 Sensor | ESP8266 NodeMCU |
|:------------:|:---------------:|
| VCC          | 3.3V            |
| DATA         | **D5**          |
| GND          | GND             |

<img width="1452" height="1083" alt="image" src="https://github.com/user-attachments/assets/e55927c0-b375-4423-ac3a-778a2eac822a" />


![Circuit diagram](docs/images/circuit-diagram.png)

More details: [docs/WIRING.md](docs/WIRING.md)

## ▶️ Quick Start

1. Clone or download this repository.
2. Open `src/esp8266_dht11_kiwisiot/esp8266_dht11_kiwisiot.ino` in Arduino IDE.
3. Edit the settings at the top of the sketch:
   ```cpp
   const char* WIFI_SSID     = "YOUR_WIFI_NAME";
   const char* WIFI_PASSWORD = "YOUR_WIFI_PASSWORD";
   const char* TOPIC_ID      = "YOUR_TOPIC_ID";
   ```
4. Select **Tools → Board → NodeMCU 1.0 (ESP-12E Module)** and the correct COM port.
5. Click **Upload**, then open the Serial Monitor at **115200** baud.

## 📊 KiwisIoT Dashboard

Create a panel and add two widgets:

| Widget      | Name        | Channel ID | Unit |
|-------------|-------------|:----------:|:----:|
| Gauge       | TEMPERATURE | 0          | °C   |
| Gauge       | HUMIDITY    | 1          | %    |

<img width="1600" height="751" alt="image" src="https://github.com/user-attachments/assets/19b5adae-15d6-4f75-9231-93ab7e25db43" />

Sending code:

```cpp
kiwisiot.send("0", temperatureData);  // Temperature
kiwisiot.send("1", humidityData);     // Humidity
```

## 📸 Real Hardware Setup

![Real hardware](docs/images/real-hardware-setup.jpg)

## 🌍 Applications

Environmental monitoring · Room monitoring · Weather monitoring · Greenhouse monitoring · Smart agriculture · Indoor climate monitoring · Automation projects

## 🎓 What You'll Learn

- Connecting a DHT11 to an ESP8266
- Reading temperature and humidity with the DHT library
- Handling invalid sensor readings
- Sending multiple values to separate KiwisIoT channels
- Configuring dashboard widgets and monitoring remotely over Wi-Fi

## 🛠️ Troubleshooting

See [docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md).

## 📁 Repository Structure

```
esp8266-dht11-kiwisiot/
├── README.md
├── LICENSE
├── .gitignore
├── src/
│   └── esp8266_dht11_kiwisiot/
│       └── esp8266_dht11_kiwisiot.ino
└── docs/
    ├── SETUP.md
    ├── WIRING.md
    ├── TROUBLESHOOTING.md
    └── images/
        ├── circuit-diagram.png
        ├── kiwisiot-dashboard.jpg
        └── real-hardware-setup.jpg
```

## 📄 License

Released under the [MIT License](LICENSE).
