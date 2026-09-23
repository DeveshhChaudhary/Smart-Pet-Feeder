# 🐾 IoT-Based Smart Pet Feeder (ESP32)

An automated, robust, and headless-capable Smart Pet Feeder built using the ESP32 microcontroller, DS3231 Real-Time Clock (RTC), SSD1306 OLED display, and Blynk IoT platform[span_0](start_span)[span_0](end_span). The system supports dynamic scheduled feeding, manual IoT triggers, real-time visual feedback, and local physical button overrides[span_1](start_span)[span_1](end_span).

---

## 📌 Features

- **Automated Sequential Dispensing:** Food servo dispenses dry kibble first, followed by a controlled 3-second water dispensing sequence[span_2](start_span)[span_2](end_span).
- **Fail-Safe Scheduling:** Runs locally using the onboard DS3231 RTC module, ensuring feeding cycles execute even during active Wi-Fi/Internet outages[span_3](start_span)[span_3](end_span).
- **Auto NTP Real-Time Sync:** Automatically synchronizes local RTC with Indian Standard Time (IST) via internet time servers upon network connection[span_4](start_span)[span_4](end_span).
- **Real-Time OLED Dashboard:** 128x64 display indicates real-time digital clock, next scheduled feeding target, and operational state[span_5](start_span)[span_5](end_span).
- **Multi-AP Wi-Fi Failover:** Supported by `WiFiMulti` routines for dynamic roaming across multiple pre-configured access points.
- **Hardware Fallback Controls:** Dedicated physical push buttons for immediate manual feed and water triggers[span_6](start_span)[span_6](end_span).

---

## 🛠️ Hardware Requirements

- **Microcontroller:** ESP32 DevKit V1 (30-pin)[span_7](start_span)[span_7](end_span)
- **Real-Time Clock:** DS3231 RTC Module (I2C)[span_8](start_span)[span_8](end_span)
- **Display:** 0.96" SSD1306 I2C OLED (128x64)[span_9](start_span)[span_9](end_span)
- **Actuators:**
  - MG90S / SG90 Micro Servo Motor (Food Dispenser Gate)[span_10](start_span)[span_10](end_span)
  - 5V Submersible Water Pump + 5V Relay Module (Active LOW)[span_11](start_span)[span_11](end_span)
- **Controls & Passive Parts:** 2x Tactile Push Buttons (Manual Feed/Water)[span_12](start_span)[span_12](end_span)
- **Mechanical Chute:** 75mm PVC Pipe, 75mm End Cap, and PVC Elbow Fitting[span_13](start_span)[span_13](end_span)[span_14](start_span)[span_14](end_span)
- **Power Supply:** 5V / 2A+ DC Power Adapter (USB-A to Type-C) with Common Ground[span_15](start_span)[span_15](end_span)

---

## 🔌 Pinout & Circuit Configuration

| Component | Pin / Signal | ESP32 GPIO | Notes / Power Rail |
| :--- | :--- | :--- | :--- |
| **DS3231 RTC** | SDA / SCL | GPIO 21 / GPIO 22 | Connected to ESP32 5V (VIN) & Common GND[span_16](start_span)[span_16](end_span) |
| **SSD1306 OLED** | SDA / SCL | Via RTC Breakout | Daisy-chained directly from secondary RTC pins[span_17](start_span)[span_17](end_span) |
| **Food Servo** | Signal (PWM) | GPIO 13 | VCC on 5V External Rail, Common GND[span_18](start_span)[span_18](end_span) |
| **Water Relay** | IN (Signal) | GPIO 14 | Active LOW configuration, Common GND[span_19](start_span)[span_19](end_span) |
| **Manual Feed** | Terminal 1 | GPIO 25 | Active LOW (`INPUT_PULLUP`), to GND[span_20](start_span)[span_20](end_span) |
| **Manual Water** | Terminal 1 | GPIO 26 | Active LOW (`INPUT_PULLUP`), to GND[span_21](start_span)[span_21](end_span) |

---

## 💻 Software & Libraries Required

Install the following libraries via the Arduino IDE Library Manager:
- `WiFi` & `WiFiMulti` (ESP32 Core)
- `Blynk` (by Volodymyr Shymanskyy)
- `ESP32Servo` (by Kevin Harrington)
- `Wire`
- `Adafruit GFX Library`
- `Adafruit SSD1306`
- `RTClib` (by Adafruit)
