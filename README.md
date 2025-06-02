# 🚚 IoT-Based Food Perish Prevention System

A smart, Arduino-based temperature-controlled container system designed to preserve perishable food items during transportation. The system uses sensors and actuators to maintain optimal environmental conditions and sends real-time data to ThingSpeak via the ESP-01 WiFi module.

---

## 📋 Features

- Monitors temperature and humidity using DHT11, LM35, and DS18B20 sensors.
- User-selectable modes for **Hot** or **Cold** storage via push buttons.
- Food type selection (Milk, Drinks, Puffs, Sandwich) for tailored temperature settings.
- Peltier module for cooling and 12V cartridge heater for heating.
- Real-time display on a 16x2 I2C LCD.
- Sends sensor data to **ThingSpeak** using ESP-01 for remote monitoring.

---

## 🧰 Hardware Components

- Arduino Uno
- ESP-01 WiFi Module
- DHT11 Temperature & Humidity Sensor
- LM35 Analog Temperature Sensor
- DS18B20 Waterproof Digital Temperature Sensor
- TEC1-12706 Peltier Module
- 12V 40W Cartridge Heater
- 2-Channel Relay Module
- 16x2 LCD with I2C Module
- Push Buttons (Hot/Cold mode + Food selection)
- 12V Fan + Heatsink
- Power Supply (12V 3A)
- Breadboard & Wires

---

## 🔌 Pin Configuration (Arduino Uno)

| Component        | Pin         |
|------------------|-------------|
| Relay - Heater   | D4          |
| Relay - Cooler   | D5          |
| Hot Mode Button  | D6          |
| Cold Mode Button | D7          |
| Sandwich Button  | D8          |
| Veg Puffs Button | D9          |
| Milk Button      | D12         |
| Cool Drinks Btn  | D13         |
| DHT11            | A0          |
| LM35             | A1          |
| DS18B20          | A2          |
| ESP-01 TX        | Connected via SoftwareSerial |
| LCD (I2C)        | SDA - A4, SCL - A5 |

---

## 📡 How It Works

1. On startup, LCD prompts the user to select **Hot** or **Cold** mode.
2. User then selects a food item (e.g., Milk, Sandwich).
3. Based on selection, system sets appropriate temperature thresholds.
4. Sensors monitor real-time temperature and humidity.
5. Arduino controls Peltier or Heater via relays.
6. Data is sent to **ThingSpeak** using ESP-01 WiFi module.

---

## 🌐 ThingSpeak Setup

1. Create an account on [ThingSpeak](https://thingspeak.com).
2. Create a new channel and enable fields for temperature and humidity.
3. Use the API Key in your Arduino code to upload data using ESP-01.

---

## 🖼️ System Overview

```plaintext
[User Input] → [Arduino] → [Sensors & Relays] → [Peltier/Heater]
                          ↓
                    [LCD Display]
                          ↓
                  [ESP-01 → ThingSpeak]
