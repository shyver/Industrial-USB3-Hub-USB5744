# Industrial 4-Port USB 3.0 Hub (High-Speed Design)

![Status: Work In Progress](https://img.shields.io/badge/Status-In_Development-orange)
![Hardware: KiCad](https://img.shields.io/badge/Hardware-KiCad_8.0-blue)
![Stackup: 4-Layer](https://img.shields.io/badge/Stackup-4--Layer-purple)
![Speed: 5 Gbps](https://img.shields.io/badge/Speed-5_Gbps-red)

## 📌 Project Overview
This repository contains the hardware design files for an industrial-grade, 4-port USB 3.0 (SuperSpeed 5Gbps) Hub. 

Designed around the **Microchip USB5744** hub controller, this project demonstrates advanced high-speed digital PCB design. It features a strict 4-layer stackup, precisely calculated 90Ω differential impedance routing, length-matching, robust ESD protection, and independent per-port power management. 

It is engineered to reliably convert a single USB-C upstream connection into four high-speed USB-A downstream ports in harsh or demanding environments.

*(Insert a screenshot of your routed PCB showing the differential pairs here later!)*

## ✨ Key Hardware Features
* **SuperSpeed Data (5 Gbps):** Full USB 3.1 Gen 1 compliance utilizing edge-coupled differential microstrip routing.
* **Impedance Control:** Mathematically calculated 90Ω differential impedance ($Z_{diff}$) tuned specifically for the JLC04161H-3313 manufacturing stackup.
* **Industrial Power Distribution:** Integrated power load switches providing dedicated, current-limited 5V power to each downstream port to prevent cascading short-circuit failures.
* **Heavy-Duty ESD Protection:** Ultra-low capacitance (< 0.5pF) TVS diode arrays on all SuperSpeed data lines to absorb transient voltage spikes without distorting multi-gigabit signal integrity.
* **Clean Clocking:** 25MHz external crystal oscillator with localized ground guarding to minimize EMI/Crosstalk.

## 📐 High-Speed PCB Specifications

To achieve reliable 5 Gbps data rates, standard 2-layer routing is insufficient. This board utilizes a custom 4-layer stackup to provide immediate, unbroken return paths for high-frequency signals.

* **Stackup Architecture:**
  * **Layer 1 (Top):** High-Speed Signals
  * **Layer 2 (In1):** Solid Ground Plane (Continuous Return Path)
  * **Layer 3 (In2):** Power Planes (5V, 3.3V, 1.2V)
  * **Layer 4 (Bottom):** Low-Speed Signals & Support Components
* **Impedance Math (USB 3.0 `SSTX`/`SSRX` & USB 2.0 `D+/D-`):**
  * Target Differential Impedance: **90 Ω ±10%**
  * Substrate Dielectric ($E_r$): **4.05**
  * Distance to Ground ($H$): **0.0964 mm**
  * Calculated Trace Width ($W$): **0.20 mm**
  * Calculated Trace Gap ($S$): **0.18 mm**

## 📂 Repository Structure
* `/Hardware` - KiCad 8.0 project files (`.kicad_sch`, `.kicad_pcb`).
* `/Docs` - Datasheets for the USB5744, Power Switches, and Ultra-low capacitance TVS diodes.
* `/Calculations` - Screenshots and data for the impedance and stackup calculations.
* `/Fabrication` - Gerber files, Drill files, BOM, and CPL files ready for PCBA.

## 🚀 Getting Started
1. Clone this repository: `git clone https://github.com/YourUsername/Industrial-USB3-Hub-USB5744.git`
2. Open the `.pro` or `.kicad_pro` file in **KiCad**.
3. *Note: Ensure your KiCad DRC rules are configured for the 4-layer constraints detailed above before modifying the layout.*

## 📝 License
This project is open-source and available under the [MIT License](LICENSE).
