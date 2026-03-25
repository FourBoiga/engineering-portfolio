# 6 GHz Antenna with Matching Network

## Overview

This project focuses on the design and simulation of a 6 GHz antenna system, including impedance matching and radiation optimization. The antenna was developed and analyzed using electromagnetic simulation tools, with PCB implementation currently in progress.

---

## Design Goal

Design a high-efficiency antenna operating at 6 GHz with:
- 13-15 dbi of gain
- Efficiency above 60%
- Have an s11 < -10
- Filter network the filters out all signals other than 5.6ghz to 6.4ghz with a center frequency of 6ghz
- Remain within a total budget of $180; this goal explicitly researves budget for multiple PCB iterations, acknoledging that RF matching networks rarely function optimally on the first revision.
- - PCB: $90
- -  Antenna: $60
- - Connectors + misc: $30

---

## Tools Used

- openEMS (electromagnetic simulation)
- KiCad (PCB design)

---

## Key Results

The simulated antenna achieved the following performance:

- **Aperture Efficiency:** 91.4755%
- **Directivity:** 15.0827 dBi  
- **Input Resistance:** 48.62 Ω  
- **Reactance:** +0.94j Ω  
- **S11 (Return Loss):** -35 dB at target frequency  

These results indicate strong impedance matching and highly efficient radiation at 6 GHz.

---

## Simulation Results

The antenna was simulated to evaluate impedance matching, radiation characteristics, and wave propagation behavior.

---

### S-Parameters

<p align="center">
  <img src="images/s_parameter.png" width="60%">
</p>

*Figure 1: Simulated S11 parameter showing approximately -35 dB return loss at 6 GHz, indicating excellent impedance matching.*

---

### 2D Radiation Patterns

<p align="center">
  <img src="images/2d_electrical_far_field.png" width="45%">
  <img src="images/2d_far_field_pattern.png" width="45%">
</p>

*Figure 2: 2D far-field radiation patterns illustrating directional energy distribution.*

---

### 3D Radiation Patterns

<p align="center">
  <img src="images/3d_electrical_far_field.png" width="45%">
  <img src="images/3d_viewport.png" width="45%">
</p>

*Figure 3: 3D radiation pattern and simulation visualization of antenna performance.*

---

### Wave Propagation Visualization

A time-domain simulation showing electromagnetic wave propagation from the antenna at 6 GHz.

<p align="center">
  <a href="https://youtu.be/U8itqUXPRIE">
    <img src="https://img.youtube.com/vi/U8itqUXPRIE/maxresdefault.jpg" width="70%">
  </a>
</p>

*Figure 4: Electromagnetic wave propagation transitioning from near-field reactive behavior to radiating far-field energy.*

Click to watch full video

---

## Engineering Analysis

The antenna demonstrates strong performance across multiple key metrics. The input impedance is close to 50 Ω with minimal reactive component, enabling efficient power transfer. The -35 dB S11 indicates extremely low reflection at the operating frequency.

The high aperture efficiency (over 90%) and directivity (~15 dBi) suggest that the antenna effectively converts input power into radiated electromagnetic energy with strong directional characteristics.

Wave propagation analysis confirms the expected transition from near-field energy storage to far-field radiation, validating the physical behavior of the design.

---

## Current Status

- Antenna design: complete (simulation)
- Matching characteristics: validated
- PCB layout: in progress
- Fabrication and testing: planned

---

## Future Work

- Fabricate PCB and validate measurements experimentally
- Compare measured vs simulated S-parameters
- Optimize bandwidth and matching network
- Integrate filtering for improved signal quality
