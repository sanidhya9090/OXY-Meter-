# IoT-Based Pulse Oximeter (Heart Rate & SpO2 Monitor)

A low-cost, breadboard-based pulse oximeter built using an **ESP8266 NodeMCU**, a **MAX30100** optical sensor, and a **0.96" SSD1306 OLED** display[cite: 1]. Both the sensor and display share a single I2C bus, keeping the circuit minimal and solder-free[cite: 1].

> **Disclaimer:** This is an educational prototype developed for academic purposes[cite: 1]. It is **not** a clinically calibrated medical device and must not be used for medical diagnosis or health decisions[cite: 1].

---

## Features
- **Real-Time Vital Monitoring:** Measures heart rate (bpm) and blood oxygen saturation (SpO2 %) from a fingertip via Photoplethysmography (PPG)[cite: 1].
- **Dual Output:** Displays live readings and status prompts on a 128×64 OLED screen alongside Serial Monitor logging at `115200` baud[cite: 1].
- **Shared I2C Bus:** Connects both the MAX30100 (`0x57`) and SSD1306 OLED (`0x3C`) using only two data pins (`D1` and `D2`)[cite: 1].

---

## Hardware Components
- **ESP8266 NodeMCU (ESP-12E)** – Microcontroller (3.3 V logic)[cite: 1]
- **MAX30100 Pulse Oximeter Module** – Red (660 nm) & IR (940 nm) LEDs with photodetector[cite: 1, 2]
- **0.96" I2C OLED Display (SSD1306)** – 128×64 pixel screen[cite: 1]
- **830-Point Breadboard & Jumper Wires**[cite: 1]
- **Micro-USB Data Cable**[cite: 1]

---

## Pin Connections

| Signal | NodeMCU Pin | MAX30100 Pin | OLED Pin |
| :--- | :--- | :--- | :--- |
| **3.3 V Power** | `3V3` | `VIN` | `VCC` |
| **Ground** | `G` (GND) | `GND` | `GND` |
| **I2C Clock (SCL)** | `D1` (GPIO5) | `SCL` | `SCL` |
| **I2C Data (SDA)** | `D2` (GPIO4) | `SDA` | `SDA` |

*Note: Power the MAX30100 strictly with `3V3` (not 5 V), and leave boot-mode pins (`D3`, `D4`, `D8`) disconnected[cite: 1].*

---

## Quick Setup
1. **Arduino IDE Setup:**
   - Add `https://arduino.esp8266.com/stable/package_esp8266com_index.json` in **File → Preferences → Additional Boards Manager URLs**[cite: 1].
   - Install the **esp8266** board package (`v3.1.2`) and select **NodeMCU 1.0 (ESP-12E Module)**[cite: 1].
2. **Required Libraries:**
   - `Adafruit SSD1306`[cite: 1]
   - `Adafruit GFX Library`[cite: 1]
   - `Adafruit BusIO`[cite: 1]
   - `MAX30100lib` (by OXullo Intersecans)[cite: 1]
3. **Upload & Run:**
   - Open the `.ino` file from the `Code/` folder, select your COM port (`115200` baud), and upload[cite: 1].
   - Place a fingertip lightly on the MAX30100 sensor and hold still for 10–20 seconds for readings to stabilize[cite: 1].

---

## Repository Structure
- `Code/` – Arduino firmware (`.ino`)[cite: 1]
- `Images/` – Circuit diagram, block diagram, and hardware photos[cite: 1]
- `PPT/` – Project presentation slides[cite: 1]
- `Report/` – Detailed project documentation (`.docx` / `.pdf`)[cite: 1]
- `Video/` – Working prototype demonstration[cite: 1]

---

## Team & Credits
**Course:** Signals and Systems (`UEC5002`) – Department of Electrical & Electronics Engineering, Shri Ramswaroop Memorial University (Session 2026–2027)[cite: 1]  
**Submitted to:** Dr. Manju Bhardwaj[cite: 1]  
**Team Members:** Sanidhya Prajapati, Krishna Awasthi, Rishikesh, Anurag[cite: 1]
