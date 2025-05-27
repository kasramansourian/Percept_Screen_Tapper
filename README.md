# Screen Tapper & Alert System for Medtronic Percept Devices

This repository contains files for a **customizable screen tapping device** designed for prolonged local field potential (LFP) recordings using the **Medtronic Percept™ devices**. The system automates screen tapping at varrying intervals and alerts the user when abnormalities are detected via a photodiode sensor.

---

## 🔧 Required Materials

### Medtronic Equipment
- Medtronic Clinician Tablet  
- Medtronic Clinician Telemetry Module (CTM) 
- Medtronic Device Charger  

### Microcontroller & Power
- [Arduino Uno](https://store-usa.arduino.cc/products/arduino-uno-rev3?utm_source=google&utm_medium=cpc&utm_campaign=US-Pmax&gad_source=1&gad_campaignid=21317508903&gbraid=0AAAAACbEa85ZTJgGHZvlyDcPqG6pQrOLn&gclid=Cj0KCQjwxdXBBhDEARIsAAUkP6ikK4L042KB6nHZxpK468FCBXPmFXHoZRnJpiLurr59JMPf5aQERZwaAhOKEALw_wcB)
- [USB Type A to Type B Cable](https://store.arduino.cc/products/usb-2-0-cable-type-ab?gQT=2)  
- [24V Power Adapter](https://www.amazon.com/XWNV-Switching-Supply-Adapter-5-5x2-1mm/dp/B0CTQ11HN1/)
- USB Wall Charger  

### Custom PCB and Components
- PCB (Designed and purchased via [EasyEDA](https://easyeda.com/))  
- Buzzer  
- 6-pin Dual-Row Wire-to-Board Connector  
- 2× Micro USB-B Female Ports  
- DC Power Receptacle  
- Jumper wires  

### Peripheral Devices
- [Commercial Screen Auto Clicker](https://www.fonefunshop.com/products/auto-clicker-phone-tap-machine-tapper-liker-6-clickers-keep-screen-awake)  

### Tools
- Computer with Arduino IDE installed  
- 3D Printer (for custom casing)  
- Soldering Iron + Supplies 

---

## ⚙️ Device Functionality

The Arduino is programmed using the Arduino IDE and performs the following functions:

- Triggers **Tapper 1(Pin 13)** every **1 hour**, with a 5-second follow-up signal  
- Triggers **Tapper 2(Pin 11)** every **10 minutes**  
- Monitors a **photodiode input** and activates a **buzzer alert** if abnormal activity is detected  

Power is supplied via a 24V wall adapter (with USB conversion), with optional battery pack for backup power.

---

## 🖥 PCB Overview

The PCB includes:
- Two Micro USB-B ports for tapper connections  
- One 6-pin dual-row wire-to-board connector  
- DC barrel jack input  
- Buzzer for photodiode signal alerts  

### 6-Pin Connector Mapping:
- **Top left pin**: Signal to **Top USB Port** (1-hour interval)  
- **Second pin**: Signal to **Bottom USB Port** (10-minute interval)  
- **Bottom right pin**: Shared **ground** for both USB ports, power input, and buzzer  

Soldering was completed in-house using the components listed in the Bill of Materials.

---

## 🧰 3D-Printed Casing

The printed case:
- Holds the clinician tablet alongside the Arduino and PCB assembly  
- Includes openings for USB and DC power connections  
- Allows wire access from Arduino to PCB  
- Mounts a flexible photodiode arm at a central screen position for optimal detection  

A **light shield** can slide on the photodiode arm to reduce false alerts from ambient light.

---

## 💻 Programming Notes

- Arduino code is uploaded using the Arduino IDE  
- Adjust timing intervals and photodiode threshold values in the `.ino` script  
- Ensure correct board and COM port are selected during upload  

---

## 📁 File Contents

