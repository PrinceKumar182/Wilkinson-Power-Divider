# ⚡ Equal Split Wilkinson Power Divider (1 GHz)

An RF/Microwave engineering project involving the design, simulation, and S-parameter analysis of an **Equal Split (3 dB) Wilkinson Power Divider** operating at a center frequency of **1 GHz** using Keysight Advanced Design System (ADS).

---

## 📌 Product Overview

The **Wilkinson Power Divider** is a passive microwave circuit component used to split an input signal into two equal-phase, equal-amplitude output signals while maintaining impedance matching at all ports and providing high isolation between output ports. 

### Key Features & Engineering Objectives:
- **Equal Power Division**: Splits input signal (Port 1) equally into two output ports (Port 2 and Port 3) with a $3\text{ dB}$ power drop.
- **Port Matching**: Achieves matched input/output impedances ($Z_0 = 50\ \Omega$) across all ports ($S_{11}, S_{22}, S_{33} \ll -20\text{ dB}$).
- **High Output Isolation**: Integrates an internal $100\ \Omega$ isolation resistor between output ports to suppress cross-talk and reflections ($S_{23} \ll -20\text{ dB}$).
- **Microstrip Line Realization**: Designed on an FR-4 / Substrate specification using Quarter-Wave ($\lambda/4$) transformer arms.

---

## 🏗️ Circuit Design & Architecture

The Wilkinson Power Divider uses two quarter-wavelength transmission line transformers ($Z_{\text{line}} = \sqrt{2} Z_0 \approx 70.71\ \Omega$) connected in parallel from Port 1 to Ports 2 and 3, along with a isolation resistor $R = 2 Z_0 = 100\ \Omega$ connected across the output nodes.

```mermaid
flowchart LR
    P1[Port 1 <br/> Z0 = 50 Ω] --> TL1["λ/4 Transformer <br/> Z = 70.71 Ω (TL2)"] --> P2[Port 2 <br/> Z0 = 50 Ω]
    P1 --> TL2["λ/4 Transformer <br/> Z = 70.71 Ω (TL3)"] --> P3[Port 3 <br/> Z0 = 50 Ω]
    P2 <--->|R = 100 Ω Isolation Resistor| P3
