
🐾 IoT-Based Smart Pet Feeder (ESP32)
An automated and IoT-enabled Smart Pet Feeder built using the ESP32 microcontroller, DS3231 Real-Time Clock (RTC), SSD1306 OLED display, servo motor, water pump, and Blynk IoT platform.
The system provides scheduled feeding, automatic food and water dispensing, remote control through Blynk, real-time OLED feedback, and physical button controls. The DS3231 RTC allows scheduled feeding to continue locally even when Wi-Fi or internet connectivity is unavailable.

📌 Project Overview
The IoT-Based Smart Pet Feeder is designed to automate the daily feeding process for pets.
The ESP32 acts as the central controller and communicates with the DS3231 RTC, OLED display, servo motor, relay-controlled water pump, physical buttons, and Blynk IoT platform.
The system can:
Dispense food automatically at scheduled times.
Dispense water after the food dispensing cycle.
Allow manual feeding using physical buttons.
Allow remote feeding through the Blynk IoT application.
Display the current time and system status on an OLED.
Synchronize time using NTP when internet connectivity is available.
Continue scheduled feeding using the DS3231 RTC during internet outages.

🎯 Objectives
Automate the feeding process for pets.
Provide scheduled food dispensing.
Provide automatic water dispensing.
Allow manual food and water control.
Enable remote control through Blynk IoT.
Maintain accurate feeding schedules using an RTC.
Provide real-time system information through an OLED display.
Ensure scheduled operation even during internet connectivity problems.

⭐ Features
🍖 Automated Food Dispensing
The servo motor operates the food dispensing mechanism and releases dry pet food according to the configured feeding schedule.
💧 Automatic Water Dispensing
After the food dispensing sequence, the water pump is activated for a controlled duration of approximately 3 seconds.
⏰ RTC-Based Scheduling
The DS3231 RTC maintains accurate time and allows the feeding schedule to operate locally.
📡 NTP Time Synchronization
When internet connectivity is available, the ESP32 can synchronize the local time with an NTP server using Indian Standard Time (IST).
📱 Blynk IoT Control
Users can manually trigger food and water dispensing through the Blynk IoT application.
🖥️ OLED Dashboard
The SSD1306 OLED displays information such as:
Current time
Next scheduled feeding
System status
Feeding operation
🔘 Physical Controls
Dedicated physical push buttons provide manual food and water controls without requiring the mobile application.

📶 Wi-Fi Failover
The system supports multiple configured Wi-Fi access points using WiFiMulti.
🛡️ Internet-Outage Operation
Scheduled feeding does not depend entirely on an active internet connection because the DS3231 RTC handles the local timing.
