# SCAR — Smart Capsular Adherence Ring (Telemetry Prototype)

SCAR is an edge-based biomedical telemetry prototype designed to monitor post-cataract surgery recovery in real time. The system acts as a wireless diagnostic testbed to monitor intraocular lens (IOL) stability and track localized thermal micro-shifts.

---

## 📌 Project Overview
Following cataract surgery, capsular contraction forces can threaten intraocular lens alignment, while silent post-operative inflammation poses severe risks if undetected. 

SCAR combines direct mechanical force sensing, thermal biomarker tracking, and battery-free NFC telemetry into an anatomical ring testbed—transforming passive ocular implants into actively monitored diagnostic devices.

---

## 🛠️ Hardware & Circuit Architecture
* **Microcontroller:** ESP32-C3 Super Mini
* **NFC Transceiver:** PN532 Module (Configured over I2C)
* **Force Transducer:** FSR402 Piezoresistive Force-Sensing Resistor (10kΩ Voltage Divider)
* **Thermal Sensor:** NTC 10kΩ Thermistor (10kΩ Voltage Divider)
* **Enclosure:** 3D-Printed Ring Prototype (50mm × 50mm × 18mm, Gyroid Infill)

---

## ⚡ Data Pipeline & NFC Telemetry
1. **Sampling:** ESP32-C3 samples analog telemetry signals from GPIO 0 (FSR402) and GPIO 1 (NTC Thermistor).
2. **Formatting:** Data is converted into a structured NDEF text payload:
   `SCAR|P:[Voltage]|T:[Celsius]`
3. **Transmission:** Updated real-time to the PN532 chip, allowing any NFC-enabled smartphone or reader to tap and fetch live diagnostics wire-free.

---

## 🚀 Future Engineering Roadmap (Micro-Scale Integration)
* Transitioning discrete FSR/NTC sensors to **capacitive MEMS pressure transducers**.
* Replacing generic microcontrollers with a custom **ASIC (Application-Specific Integrated Circuit)**.
* **ISO 10993 medical-grade silicone/acrylic** micro-encapsulation for clinical feasibility.

---

## 📂 Repository Structure
