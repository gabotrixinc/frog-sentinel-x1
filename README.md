**Frog Sentinel X1 - Autonomous Environmental Monitoring Platform**  
Important: This repository is under construction. It is possible that the complete information is not yet available.
---

## **Overview**  
The **Frog Sentinel X1** is an open-source IoT platform designed for long-term environmental monitoring in extreme conditions. Built around Nordic Semiconductor's **nRF9151 SiP**, it combines LTE-M/NB-IoT connectivity, solar harvesting, and modular sensor integration to enable global deployments for climate research, agriculture, and disaster prevention.  

**Key Features:**  
🌍 **Global Connectivity**: LTE-M/NB-IoT + GNSS (GPS/Galileo)  
🔋 **Energy Autonomous**: 95% efficient MPPT solar harvesting (BQ25504) + supercapacitor backup  
🧩 **Modular Design**: STEMMA QT/Qwiic connectors for plug-and-play sensors (SCD41, SHT40, etc.)  
📡 **Scalable Network**:  LoRa communication with **Nano Frogs** (ultra-compact sensor nodes)  

**[Download Full BOM & Schematics](docs/Frog_Sentinel_X1_BOM_v2.0.pdf)**  

---

## **Hardware Architecture**  
Block Diagram  

### **Core Components**  
| **Module**          | **Key Components**                                  |  
|---------------------|----------------------------------------------------|  
| **Connectivity**    | nRF9151 SiP (LTE-M/NB-IoT + GNSS), LoRa SX1262 (Optional) |  
| **Power Management**| BQ25504 PMIC, TPS62840 Buck Converter, 5F Supercapacitor |  
| **Sensors**         | STEMMA QT ports, Integrated Antenna Fractal Design | 
| **LoraWAN**         | Semtech/SX1262IMLTRT - LoraWAN Transceiver | 

---

## **Getting Started**  

### **1. Prerequisites**  
- **Hardware**: [Frog Sentinel X1 PCB](hardware/gerber), LiPo Battery (3.7V 1000mAh), Solar Panel (5V/90mA)  
- **Software**: [nRF Connect SDK v2.0.2+](https://developer.nordicsemi.com/), Zephyr OS, VS Code  

### **2. Flashing Firmware**  
```bash
git clone https://github.com/ribbit-network/frog-sentinel-x1.git
cd firmware
west build -b nrf9151dk_nrf9151 -- -DSHIELD=frog_sentinel_x1
west flash
```

### **3. Cloud Integration**  
1. **Ribbit Cloud Suite**: Configure your API keys in `config/cloud_config.h`  
2. **MQTT Topics**:  
   - `ribbit/sentinel/[DEVICE_ID]/telemetry` (Sensor Data)  
   - `ribbit/sentinel/[DEVICE_ID]/commands` (Remote OTA Updates)  

---

## **Nano Frogs (Add-On)**  
Deploy ultra-compact sensor nodes using our **Nano Frog PCB Design**:  
- **Size**: 2x2cm  
- **Sensors**: SCD41 (CO₂) + SHT40 (T/H)  
- **Communication**: LoRa 868MHz (2-5km range)  

[View Nano Frog Repository](https://github.com/gabotrixinc/nano-frog)  

---

## **Contributing**  
We welcome contributions! Please follow these steps:  
1. Fork the repository  
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)  
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)  
4. Push to the branch (`git push origin feature/AmazingFeature`)  
5. Open a Pull Request  

Report bugs via [GitHub Issues](https://github.com/gabotrixinc/frog-sentinel-x1/issues).  

---

## **License**  
This project is licensed under **CC BY-SA 4.0**. Commercial use requires written permission.  

[License  

---

## **Acknowledgments**  
- Nordic Semiconductor for nRF9151 technical support  
- Texas Instruments for BQ25504/TPS62840 reference designs  
- Taoglas for fractal antenna design guidance  

**Let’s build a sustainable future together!** 🌱🐸  

---  
**Visit website**: [ribbitnetwork.org](https://ribbitnetwork.org) 
