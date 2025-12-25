# WM-Tanishq_Sugandhi-IFHE_University
Smart Waste Bin Monitoring and Collection Optimization System using Arduino, ESP32, and LoRa for smart city applications (Virtual IoT Design Challenge – IIITH).

# Smart Waste Bin Network  
### Virtual IoT Design Challenge – Smart City Living Lab, IIITH

## Project Overview
Urban waste management systems often suffer from inefficient collection schedules, leading to overflowing bins in some areas and unnecessary trips in others. This project proposes and demonstrates a **Smart Waste Bin Monitoring and Collection Optimization System** using IoT technologies to monitor bin fill levels in real time and assist authorities in optimizing waste collection routes.

The solution leverages **low-power sensors, LoRa communication, and edge intelligence** to create a scalable and cost-effective smart city application.

---

## Objectives
- Detect and monitor the fill level of waste bins across city zones  
- Notify authorities when bins are nearly full  
- Enable data-driven and optimized waste collection routing  
- Reduce operational costs and improve urban hygiene  

---

## System Architecture

### 1. Smart Bin Node
- **Microcontroller:** Arduino UNO  
- **Sensor:** HC-SR04 Ultrasonic Sensor  
- **Communication Module:** SX1278 LoRa (433 MHz)  
- **Function:**  
  - Measures bin fill level  
  - Converts distance to fill percentage  
  - Transmits data wirelessly via LoRa  

### 2. Gateway Node
- **Microcontroller:** ESP32  
- **Communication Module:** SX1278 LoRa  
- **Function:**  
  - Receives bin data  
  - Displays fill level and alerts  
  - Acts as interface to cloud/dashboard (conceptual)  

---

## Data Flow
1. Ultrasonic sensor measures distance to waste surface  
2. Arduino UNO calculates fill percentage  
3. Data transmitted via LoRa (SX1278)  
4. ESP32 gateway receives data  
5. Alerts generated when fill level exceeds threshold  
6. Data visualized on dashboard (conceptual cloud layer)

---

## Communication Protocol
- **LoRa (Long Range, Low Power):**
  - Suitable for city-wide deployments  
  - Low energy consumption  
  - High scalability  

- **MQTT (Conceptual – Cloud Layer):**
  - Lightweight publish/subscribe protocol  
  - Ideal for IoT telemetry and alerts  

---

## Route Optimization Strategy

### Priority-Based Collection Logic
- **High Priority:** Fill level ≥ 80%  
- **Medium Priority:** 60–80%  
- **Low Priority:** < 60%  

### Optimization Approach
- Zone-wise bin clustering  
- Priority-based scheduling  
- Shortest-path / greedy routing for garbage trucks  

### Pseudocode

For each bin:
    If fill_level >= 80%:
        Mark as HIGH priority

Group bins by zone
Sort bins by priority and distance
Generate optimized collection route

---

## Power Management Strategy
- Periodic sensing (every 30–60 minutes)  
- Low-power LoRa communication  
- Microcontroller sleep modes (future enhancement)  
- Event-based data transmission  
- Optional solar-assisted charging  

---

## 🛡️ Reliability & Fault Handling
- Multiple sensor readings averaged to avoid false values  
- Software filtering to ignore sudden spikes  
- Detection of abnormal or constant readings  
- Periodic calibration and maintenance alerts  

---

## 📈 Scalability & Network Design
- Supports **100+ bins across multiple city zones**  
- **Star topology:** Bin Nodes → Gateway → Cloud  
- Easy deployment, low maintenance, and scalable architecture  

---

## Cost & Feasibility

### Approximate Cost per Bin
| Component | Cost (INR) |
|---------|------------|
| Arduino UNO | ₹450 |
| Ultrasonic Sensor | ₹150 |
| SX1278 LoRa Module | ₹500 |
| Battery & Enclosure | ₹300 |
| **Total** | **₹1400–1500** |

### Trade-offs
- Higher accuracy increases cost  
- Lower cost slightly reduces precision  
- Proposed design balances affordability, scalability, and reliability  

---

## Prototype Implementation
A functional prototype was developed using:
- **Arduino UNO + Ultrasonic Sensor + SX1278 LoRa** as the Smart Bin Node  
- **ESP32 + SX1278 LoRa** as the Gateway Node  

The prototype successfully demonstrates:
- Real-time bin fill level detection  
- Wireless data transmission  
- Alert generation for near-full bins  

---

## Future Enhancements
- Cloud integration (AWS / Firebase / ThingsBoard)  
- Web & mobile dashboards  
- GPS-enabled truck tracking  
- AI-based waste generation prediction  

---

## Author
**Tanishq Sugandhi**  
Engineering Student 
Virtual IoT Design Challenge – Smart City Living Lab, IIITH
