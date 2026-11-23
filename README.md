# Designing-Fridge-Humidity-Temperature-Sensor-with-PCB-Model


A custom wireless environmental monitoring system designed to track refrigerator temperature and humidity in real time. Built around the **ATmega328P** microcontroller, this project consists of a battery-powered **Transmitter** unit placed inside the fridge and a **Receiver** display unit positioned outside.

---

## System Architecture

### 1. Transmitter Unit (`Fridge_Transmitter`)
The transmitter unit collects ambient temperature and relative humidity data inside the refrigerator and broadcasts it wirelessly via an RF transmitter module.
* **Microcontroller:** ATmega328P (with external crystal oscillator & 22pF load capacitors)
* **Sensor:** AM2302 (DHT22) Digital Temperature & Humidity Sensor with 10kΩ pull-up resistor
* **Wireless Module:** 4-pin RF Transmitter module with external antenna (`AE1`)
* **Power Supply:** 9V battery input with dual Zener-regulated rails (**5V** via `D1` and **3.3V** via `D2`) and 100µF decoupling capacitors
* **Controls:** Tactile reset push-button (`SW2`) with 10kΩ pull-up and 100nF debounce capacitor

### 2. Receiver Unit (`Fridge_Receiver`)
The receiver unit captures incoming RF packets from the transmitter, processes the telemetry data, and displays the readings locally.
* **Microcontroller:** ATmega328P clocked by a 16MHz crystal oscillator (`Y1`)
* **Wireless Module:** RF Receiver module (`J1`) with external antenna (`AE1`)
* **Display:** 16x2 Character LCD (`LCD-016N002L`) operating in 4-bit mode (`DB4–DB7`) with a 10kΩ contrast adjustment potentiometer (`RV1`)
* **Power Supply:** 9V battery regulated down to a stable **5V** rail using an **L7805** linear voltage regulator (`U3`) with 470µF, 10µF, and 100nF filtering capacitors
* **Controls:** Tactile reset push-button (`SW1`)

---

## Tools & Workflow
* **EDA Software:** KiCad (Schematic Capture & KiCad PCB Layout)
* **Hardware Design:** Through-Hole (THT) & SMD mixed prototyping, DRC/ERC verified

* ## Documentary
* <img width="596" height="571" alt="Fridge_Transmitter Schematic" src="https://github.com/user-attachments/assets/6203974a-2985-4c18-ab71-bd891e5342cc" />
Image 1. Transmitter Schematic

<img width="624" height="519" alt="Fridge_Transmitter PCB" src="https://github.com/user-attachments/assets/ef6047cf-36ab-43ac-b182-ad5b508c6e87" />
Image 2. Transmitter PCB Model

<img width="577" height="464" alt="Fridge_Transmitter top" src="https://github.com/user-attachments/assets/1e087187-6aa4-48ef-9f12-c70ee78151f1" />
Image 3. Top Look

<img width="572" height="488" alt="Fridge_Transmitter bottom" src="https://github.com/user-attachments/assets/ac721bc0-15b4-4fca-97bd-f8a22e82a304" />
Image 4. Bottom Look

<img width="763" height="568" alt="Fridge_Receiver Schematic" src="https://github.com/user-attachments/assets/03ed81e1-ed84-47ae-9c69-a4be887d17e8" />
Image 5. Receiver Schematic

<img width="705" height="522" alt="Fridge_Receiver PCB" src="https://github.com/user-attachments/assets/230a4208-f1f0-4512-b3c0-7485b5d5b731" />
Image 6. Receiver PCB

<img width="572" height="488" alt="Fridge_Transmitter bottom" src="https://github.com/user-attachments/assets/5925e903-6aaa-491e-b66f-bfa6611c71ab" />
Image 7. Top Look

<img width="555" height="411" alt="Fridge_Receiver Bottom" src="https://github.com/user-attachments/assets/9cbeaa70-1eaa-453e-b125-969a400b94e6" />
Image 8. Bottom Look
