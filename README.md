# Integrated-Paperfluidic-Platform-for-CRISPR-Diagnostics-of-TB
A multi-device embedded control system designed for precise temperature regulation and fluorescence intensity control, suitable for application such as paper-based diagnostics.
The system integrates:
* Closed-loop temperature control using PID
* Adjustable fluorescence LED intensity
* Real-time monitoring and control via Raspberry Pi

# Objectives
* Develop a portable CRISPR fluorescence detection system
* Maintain precise thermal control at 39 °C using PID regulation
* Integrate heating, illumination, and imaging into a unified platform
* Enable adaptive LED intensity control for fluorescence excitation
* Implement real-time monitoring and control via local and remote interfaces
* Acquire and facilitate analysis of fluorescence signals using imaging techniques

# System Architecture
* **Communication Structure**
  <img width="1032" height="540" alt="image" src="https://github.com/user-attachments/assets/300238db-6551-4fff-9156-5d1f6784fd51" />

* **Functional Blocks**
  * Arduino UNO --> Temperature sensing + PID heater control
  * ESP 32 --> LED intensity control via web server
  * Raspberry Pi --> Central control

# Hardware Components
* **Controller Units**
  * Raspberry Pi
  * Arduino UNO
  * ESP32
* **Sensors**
  * DS18B20 Temperature Sensor
  *  Heating Element
  *  High-power green LED
  *  LED Driver

# Software Stack
* Arduino IDE
* HTTP Communication (ESP32)
* Serial Communication (UNO)
* Python (Raspberry Pi)

# Working Principle
* **Temperature Control (UNO)**
  * Reads temperature using **DS18B20**
  * Uses **PID control** to maintain 39°C
  * Adaptive heating:
    * Full power when far from setpoint
    * PID near target
    * Soft control near stability
* **LED Control (ESP32)**
  * Hosts a **web server**
  * Receives HTTP commands:
    * LOW
    * MEDIUM
    * HIGH
    * OFF
  * Adjusts PWM output accordingly
* **Central Control (Raspberry Pi)**
  * Reads temperature from UNO via serial
  * Sends heater commands (HEATER_ON, HEATER_OFF)
  * Sends LED commands via HTTP requests
  * Provides:
    * Web interface
    * GUI interface
* **Web API Endpoints**
  
* **Graphical User Interface**
  Features:
  * Real-time temperature display
  * Heater ON/OFF control
  * LED intensity buttons
  * Simple and responsive interface
**Example Outpu**

# Installation & Setup
* **1. Upload Firmware**
 * Upload ESP32 code: 
* 
