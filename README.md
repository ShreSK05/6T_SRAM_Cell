# 6T CMOS SRAM Cell – LTspice Simulation (180nm Technology)

---

## 📌 Project Overview

This project presents the design and simulation of a 6-Transistor (6T) CMOS SRAM cell using 180nm CMOS technology in LTspice.

The SRAM cell consists of:
- Two cross-coupled CMOS inverters
- Two access NMOS transistors
- Differential bitlines (BL and BLB)
- Wordline control signal

Supply voltage is 1.8 V and bitlines are precharged to 1.8 V.

---

## ⚙️ Circuit Parameters

| Parameter | Value |
|------------|--------|
| Technology Node | 180 nm |
| VDD | 1.8 V |
| Channel Length (L) | 180 nm |
| Pull-Up PMOS (M1, M2) | 2 µm / 180 nm |
| Pull-Down NMOS (M3, M4) | 1 µm / 180 nm |
| Access NMOS (M5, M6) | 1.2 µm / 180 nm |
| Bitline Capacitance | 150 fF |
| Wordline Signal | PULSE (0 → 1.8 V) |

All transistors use minimum channel length (L = 180 nm).

---

## 🔢 Transistor Ratio Calculations

### 1. Cell Ratio (CR)

Definition:

CR = (W/L)_pull-down / (W/L)_access

Since L is same for all devices:

CR = W_pull-down / W_access  
CR = 1 / 1.2  
CR = 0.83  

---

### 2. Pull-Up Ratio (PR)

Definition:

PR = (W/L)_access / (W/L)_pull-up  

Since L is constant:

PR = W_access / W_pull-up  
PR = 1.2 / 2  
PR = 0.6  

---

## 📊 Static Noise Margin (SNM)

### 1. Hold SNM

Definition:

SNM_hold = (V_trip1 − V_trip2) / 2  

From DC butterfly curve simulation:

SNM_hold ≈ 0.24 V  
SNM_hold ≈ 240 mV  

---

### 2. Read SNM

Definition:

SNM_read = (V_read-trip1 − V_read-trip2) / 2  

From simulation:

SNM_read ≈ 0.18 V  
SNM_read ≈ 180 mV  

---

## 🔋 Write Margin (WM)

Definition:

WM = VDD − V_flip  

From simulation:

WM ≈ 0.35 V  
WM ≈ 350 mV  

---

## 🔋 Leakage Current Analysis

### Subthreshold Leakage Equation

I_sub = I0 × exp((V_GS − V_th) / (n V_T))  

Where:  
V_T = kT/q  
n = subthreshold slope factor  

Measured standby leakage (hold mode):

I_leakage ≈ 18 nA – 35 nA  

---

## ⚡ Standby Power

P_standby = VDD × I_leakage  

P_standby = 1.8 × 35 nA  
P_standby ≈ 63 nW  

---

## 🔍 Operating Condition Summary

| Quantity | Value |
|------------|--------|
| Hold SNM | ≈ 240 mV |
| Read SNM | ≈ 180 mV |
| Write Margin | ≈ 350 mV |
| Standby Leakage | 18 – 35 nA |
| Standby Power | ≈ 63 nW |
| Cell Ratio (CR) | 0.83 |
| Pull-Up Ratio (PR) | 0.6 |

---

## 🛠 Simulations Performed

- Transient analysis (Read / Write / Hold)
- DC sweep analysis (Butterfly curve extraction)
- Leakage current measurement
- Stability verification under 150 fF bitline loading

---

## 📐 Device Operation

- Cross-coupled inverters provide bistable storage.
- Access NMOS transistors connect internal nodes to BL and BLB during read/write.
- Pull-down NMOS ensures read stability.
- Pull-up PMOS ensures data retention during hold.
- Devices operate in saturation region during stable hold condition.

---
