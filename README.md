# AgroSetu IOT 

## Overview

This repository contains the IoT component of a comprehensive solution designed to empower smallholder farmers, particularly in India, as part of the Google Solution Challenge. The system integrates solar-powered IoT devices to monitor farm conditions in real-time, including soil moisture, temperature, humidity, and gas levels (using MQ3 and MQ5 sensors). Data is displayed on an LCD screen and uploaded to Firebase Realtime Database for further analysis and integration with a web/mobile app. This sustainable, affordable hardware solution enhances resource optimization and provides actionable insights to farmers.

### Key Features
- **Real-Time Monitoring**: Tracks soil moisture, temperature, humidity, and gas levels using sensors.
- **Solar-Powered Sustainability**: Designed to operate in rural areas with limited electricity access (solar integration to be implemented in hardware).
- **LCD Display**: Shows live sensor data for immediate farmer feedback.
- **Firebase Integration**: Sends data to the cloud for storage and app synchronization.
- **Scalable Design**: Affordable and adaptable for smallholder farmers.

## Hardware Requirements
- **Microcontroller**: ESP32 (Wi-Fi enabled)
- **Sensors**:
  - Soil Moisture Sensor (connected to pin 34)
  - DHT11 Temperature Sensor (connected to pin 13)
  - Humidity Sensor (connected to pin 35)
  - MQ5 Gas Sensor (connected to pin 32)
- **Display**: 16x2 I2C LCD (address 0x27)
- **Power**: Solar panel with battery (future enhancement; currently USB-powered for testing)
- **Wi-Fi**: Stable internet connection for data upload

## Software Requirements
- **Arduino IDE**: For programming the ESP32
- **Libraries**:
  - `WiFi.h` (pre-installed with ESP32 board)
  - `HTTPClient.h` (pre-installed with ESP32 board)
  - `DHT.h` (install via Library Manager)
  - `LiquidCrystal_I2C.h` (install via Library Manager)
- **Firebase**: Realtime Database setup with API key and host URL

## Installation

1. **Clone the Repository**:
   ```bash
   https://github.com/Chayan-03/AgroSetu-IOT
   ```
2.  **Set Up Hardware**:
     - Connect sensors and LCD to the ESP32 as per the pin definitions in the code.
     - Ensure proper wiring and power supply (USB or solar setup).
3. **Configure Credentials**
   - Open `main.ino` in Arduino IDE.

   Replace the placeholders in the code with your own credentials:
  
  - `ssid`: Your Wi-Fi network name
  - `password`: Your Wi-Fi password
  - `firebaseHost`: Your Firebase Realtime Database URL
  - `apiKey`: Your Firebase API key
4. **Install Libraries**

  In Arduino IDE, go to:

  ```text
  Sketch > Include Library > Manage Libraries
```
**5. Upload Code**

Select your ESP32 board in Arduino IDE:

```text
Tools > Board > ESP32 Dev Module
```
**6. Firebase Setup**

- Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com).
- Enable **Realtime Database** and note down your database URL and API key.

---

**Usage**

- Power on the ESP32; it will connect to Wi-Fi and start reading sensor data.
- Sensor values are displayed on the LCD and printed to the Serial Monitor (115200 baud rate).
- Data is sent to Firebase under the `sensor_data` node with timestamps as keys.
- Monitor Firebase for real-time updates and integrate the data with the web or mobile app.

---

**Project Structure**

- `main.ino`: Core Arduino code for sensor reading, LCD display, and Firebase upload.

---

**Future Enhancements**

- Integrate solar power with battery management for true off-grid operation.
- Add automatic irrigation control based on soil moisture thresholds.
- Enhance gas sensor calibration for specific agricultural use cases (e.g., pest detection).


