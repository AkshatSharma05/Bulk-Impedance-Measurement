# Bulk Impedance Measurement Tool
## Overview

This repository contains the PCB design for a bulk impedance measurement tool built around an ESP32, an AD9833 DDS signal generator, and the internal ADC for measurement.

The system generates a sinusoidal excitation signal, conditions and buffers it, and applies it to a voltage divider formed by a known resistor (R_known) and an external unknown impedance (Z_unknown). The ESP32 measures the input and output voltages using its ADC and computes the unknown impedance using:

```Z_unknown = R_known × (Vout / (Vin − Vout))```

<img width="704" height="811" alt="Screenshot from 2026-05-09 03-07-40" src="https://github.com/user-attachments/assets/5638d713-5db1-44f7-b73f-7a7bd33e2604" />


## Notes
- The design is intended for low-voltage impedance measurement experiments and prototyping.
- Best sensitivity is achieved when R_known ≈ Z_unknown.
- All measurements are performed using AC excitation.
- The DIP Switches provided can be used to change the value of R_known -> 1K, 10K, 100K.
