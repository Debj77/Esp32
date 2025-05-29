# Esp32
Contains IOT projects using Esp32

# 📡 IoT Project: ESP32 Fetching DHT11 Data from Web Server (JSON)

## 📝 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [System Architecture](#system-architecture)
- [How It Works](#how-it-works)
- [Getting Started](#getting-started)
- [Code Structure](#code-structure)
- [Sample Output](#sample-output)
- [Challenges Faced](#challenges-faced)
- [Future Improvements](#future-improvements)
- [License](#license)
- [Author](#author)

## 📖 Overview
This IoT project demonstrates how an ESP32 microcontroller fetches DHT11 sensor data (temperature and humidity) from a remote web server in JSON format. The ESP32 parses the data and performs conditional operations (e.g., alerts, GPIO control).

## ✨ Features
- HTTP GET request to web server
- JSON data parsing using ArduinoJson
- Real-time temperature and humidity monitoring
- GPIO control logic based on sensor values
- Easily extendable to MQTT/cloud or dashboard

## 🛠️ Hardware Requirements
| Component         | Quantity | Notes                    |
|------------------|----------|---------------------------|
| ESP32 Dev Board  | 1        | Any ESP32 model           |
| Wi-Fi Access     | 1        | Required for internet     |
| Relay/Fan Module | Optional | For automation            |
| OLED Display     | Optional | For local output display  |

## 💻 Software Requirements
- Arduino IDE (v1.8 or newer)
- ESP32 Board Support (via Board Manager)
- Required Libraries:
  - `WiFi.h`
  - `HTTPClient.h`
  - `ArduinoJson.h` (install via Library Manager)

## 📊 System Architecture

```
[DHT11 Sensor] ---> [Web Server Hosting JSON API]
                                ↑
                                |
                       [ESP32 Microcontroller]
                                ↓
            [Serial Output / GPIO Control / Alerts]
```

## ⚙️ How It Works
1. A web server hosts DHT11 sensor data in JSON format (e.g., `{"temperature": 26.4, "humidity": 65}`).
2. The ESP32 connects to Wi-Fi and sends an HTTP GET request to the server.
3. The ESP32 receives the JSON response, parses the temperature and humidity.
4. ESP32 performs logic based on the values (e.g., if temperature > 30°C, turn on fan).

## 🚀 Getting Started

### 1. Clone or Download the Project
```
git clone https://github.com/yourusername/iot-dht11-esp32-http-fetch.git
cd iot-dht11-esp32-http-fetch
```

### 2. Open the Code in Arduino IDE
- File → Open → `esp32_dht11_http.ino`

### 3. Setup Wi-Fi Credentials
Update the following lines in your code:
```cpp
const char* ssid = "YOUR_WIFI_SSID";
const char* password = "YOUR_WIFI_PASSWORD";
const char* serverURL = "http://your-server-ip-or-url/data";
```

### 4. Upload to ESP32
- Connect ESP32 via USB
- Select correct board and COM port
- Click **Upload**

## 📁 Code Structure

```
iot-dht11-esp32-http-fetch/
├── esp32_dht11_http.ino     // Main ESP32 sketch
├── images/                  // Optional hardware screenshots
├── LICENSE
└── README.md                // Project documentation
```

## 🖥️ Sample Output

### ✅ Serial Monitor
```
Connecting to WiFi...
Connected!
Fetching data from http://192.168.1.100/data
Temperature: 27.5 °C
Humidity: 64 %
Fan turned OFF
```

### 📷 Images
*(Add photos of your hardware setup and serial output here)*

## 🧩 Challenges Faced
- Handling JSON parsing errors when server response is invalid or delayed
- Reconnecting Wi-Fi in case of signal loss
- Keeping memory usage low on ESP32

## 🌱 Future Improvements
- Add MQTT support to forward data to cloud
- Store historical data in Firebase or InfluxDB
- Add OLED display for on-device output
- Mobile notification using Blynk or Telegram bot
- Create Node-RED dashboard or ThingsBoard telemetry view

## 📜 License
This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## 👤 Author
**Your Name**  
[GitHub](https://github.com/yourusername)  
[LinkedIn](https://linkedin.com/in/yourprofile)
