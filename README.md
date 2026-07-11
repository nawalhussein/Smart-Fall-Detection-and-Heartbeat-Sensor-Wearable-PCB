# ATmega32 Smart Watch & Fall Detection System

This repository contains the hardware schematics, PCB design, and bare-metal firmware for a wearable Smart Watch featuring real-time health monitoring and automated fall detection.

### Brief Project Description

This wearable device is designed to monitor user vitals and detect sudden falls, transmitting emergency data wirelessly. The system leverages an 8-bit AVR architecture optimized for low power consumption.

Key components and subsystems include:
* **Microcontroller:** An ATmega32A MCU managing sensor data acquisition, threshold calculations, and peripheral communication.
* **Inertial Measurement (Fall Detection):** An **MPU6050** 6-axis gyroscope/accelerometer connected via **I2C**. It continuously samples acceleration forces to detect sudden impacts or unusual orientation changes indicative of a fall.
* **Health Monitoring:** A **MAX30102** pulse oximeter and heart-rate sensor (also on the **I2C** bus) tracks biometric data.
* **Wireless Connectivity:** An **ESP-01 (ESP8266)** Wi-Fi module interfaces via **UART** to upload telemetry data to a cloud server or trigger remote alerts.
* **User Interface:** Features a localized notification system using a hardware buzzer, status LEDs (Green, Yellow, Red), and manual push buttons for user interaction (e.g., canceling a false alarm).
* **Power Management Network:** Designed for portability, the system runs on a **3.7V Li-ion battery** with an integrated charging module, a **Boost Converter** to step up voltage, and dedicated **5V and 3.3V regulators** to cleanly power the mixed-voltage rails.
* **In-System Programming:** Features a dedicated **USBASP** hardware header for direct ISP flashing and debugging.
