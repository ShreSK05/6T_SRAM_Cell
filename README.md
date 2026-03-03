6T CMOS SRAM Cell Design and Simulation (180nm Technology)
📌 Project Overview

This project presents the design and simulation of a 6-Transistor (6T) CMOS SRAM cell using 180nm CMOS technology in LTspice. The objective was to evaluate Read, Write, and Hold stability, extract Static Noise Margin (SNM), and measure standby leakage under realistic bitline loading conditions.

🧱 Technology and Device Parameters
Parameter	Value
Technology Node	180 nm
Supply Voltage (VDD)	1.8 V
Channel Length (L)	180 nm
Pull-Up PMOS Width	2 µm
Pull-Down NMOS Width	1 µm
Access NMOS Width	1.2 µm
Bitline Capacitance	150 fF

All transistors use minimum channel length (L = 180nm).

⚙️ Transistor Ratio Calculations
1. Cell Ratio (CR)

Definition:

CR = (W/L)pull-down / (W/L)access

Since all devices have same channel length:

CR = Wpull-down / Waccess
CR = 1 / 1.2
CR = 0.83
2. Pull-Up Ratio (PR)

Definition:

PR = (W/L)access / (W/L)pull-up

Since L is constant:

PR = Waccess / Wpull-up
PR = 1.2 / 2
PR = 0.6
📊 Static Noise Margin (SNM)
1. Hold SNM

SNM is defined as the side length of the largest square embedded inside the butterfly curve obtained from DC transfer characteristics.

Mathematically:

SNMhold = (Vtrip1 − Vtrip2) / 2

From DC sweep simulation:

SNMhold ≈ 0.24 V
SNMhold ≈ 240 mV
2. Read SNM

During read operation, the access transistor weakens the internal storage node.

SNMread = (Vread-trip1 − Vread-trip2) / 2

From simulation:

SNMread ≈ 0.18 V
SNMread ≈ 180 mV
🔍 Write Margin (WM)

Write Margin is defined as the minimum bitline voltage required to flip the stored state.

WM = VDD − Vflip

From simulation:

WM ≈ 0.35 V
WM ≈ 350 mV
📉 Leakage Current Analysis
Subthreshold Leakage Current

General equation:

Isub = I0 × exp((VGS − Vth) / (nVT))

Where:

VT = kT/q

n = subthreshold slope factor

Measured standby leakage (hold mode):

Ileakage ≈ 18 nA – 35 nA
⚡ Standby Power
Pstandby = VDD × Ileakage
Pstandby = 1.8 × 35 nA
Pstandby ≈ 63 nW
📈 DC Sweep Analysis

Performed DC voltage transfer characteristic sweep from 0 V to 1.8 V.

Butterfly curve generated using:

Vout1 = f(Vin)
Vout2 = f⁻¹(Vin)

Maximum embedded square side length extracted as SNM.

📊 Final Performance Summary
Parameter	Measured Value
Hold SNM	≈ 240 mV
Read SNM	≈ 180 mV
Write Margin	≈ 350 mV
Standby Leakage	18 – 35 nA
Standby Power	≈ 63 nW
Cell Ratio (CR)	0.83
Pull-Up Ratio (PR)	0.6
🛠 Simulations Performed

Transient analysis (functional verification)

DC sweep (Butterfly curve extraction)

Leakage current measurement

Write margin verification
