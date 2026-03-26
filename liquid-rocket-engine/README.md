# High-Pressure Liquid Rocket Engine — Ethanol / Nitrous Oxide

## Overview

This project documents the design of a small, high-pressure liquid rocket engine fueled by **ethanol** and **nitrous oxide**, entirely modeled in **Fusion 360**. The project highlights engineering reasoning, CAD-driven system design, and iterative problem solving, demonstrating both theoretical understanding and practical design skills.

The engine was conceived as a **learning-focused small-scale liquid engine**, emphasizing injector design, chamber pressure, nozzle optimization, and pump integration.

---

## Design Goals

- Explore the principles of liquid rocket propulsion using accessible fuels.  
- Design a combustion chamber and pintle injector system for stable combustion.  
- Integrate cooling channels, pump, and nozzle geometry in CAD.  
- Understand and apply historical and literature-backed designs (NASA reports, MIT Rocket Team guides).  
- Experience hands-on engineering decision-making, including trade-offs between materials, geometry, and feasibility.

---

## System Architecture

The engine consists of:

- **Combustion Chamber**: Designed for a target pressure of ~250 psi.  
- **Pintle Injector**: Provides controlled oxidizer and fuel mixing.  
- **Copper Cooling Pipes**: Ethanol-based regenerative cooling channels.  
- **Ethanol Pump**: Supplies fuel at controlled flow and pressure.  
- **Pressurized Nitrous Oxide Tank**: Maintains oxidizer in liquid state (800–1000 psi).  
- **Nozzle**: Designed for ~0.9 atm exit pressure and ~1 N thrust.

<img src="images/engine_full_assembly.png" alt="Full Engine Assembly" width="600"/>
<p align="center"><i>CAD assembly showing injector, chamber, nozzle, pump, and cooling paths.</i></p>

---

## Injector Design

The engine employs a **pintle injector**, selected for:

- Simplified CAD geometry for design and integration.  
- Efficient atomization and mixing of ethanol and nitrous oxide.  
- Historical precedent in small-scale engines.

<img src="images/engine_injector_side.png" alt="Injector Side View" width="600"/>
<p align="center"><i>Side view of pintle injector showing flow passages and central oxidizer jet.</i></p>

<img src="images/engine_injector_top.png" alt="Injector Top View" width="600"/>
<p align="center"><i>Top view of the injector, illustrating fuel annulus and oxidizer channel.</i></p>

---

## Nozzle Design & Performance

Nozzle geometry was optimized for small-scale thrust while simulating **real-world conditions**:

- **Throat Diameter**: ~1 inch.  
- **Exit Pressure**: 0.9 atm, representing **average ambient pressure** experienced by rockets across varying flight altitudes.  
- **Expansion Ratio**: Designed for efficient exhaust expansion, minimal flow separation, and predicted thrust ~1 N.  
- **Integration**: Smooth internal contours for consistent chamber-to-nozzle transition.

<img src="images/engine_nozzle_injector_slice.png" alt="Nozzle & Injector Cross-Section" width="600"/>
<p align="center"><i>Cross-section of nozzle and injector integration.</i></p>

---

## Pump Section

The engine uses an ethanol pump to feed fuel to the chamber. Key parameters:

| Parameter        | Value         | Units | Notes                                      |
|-----------------|---------------|-------|--------------------------------------------|
| Ethanol Flow Rate | 0.1313        | kg/s  | Pump-fed ethanol                           |
| Pressure Delta    | 235.3         | psi   | Across the pump                             |
| Oxidizer Feed     | 800–1000      | psi   | N₂O remains liquid at pressure             |
| Seal Type         | Self-acting   | —     | Rulon + spring, pressure-activated         |
| Bearing           | High-speed    | —     | No-lube, supports shaft rotation           |

### Pump Seal Design

The pump employs a **self-acting Rulon seal** inspired by NASA designs:

- **Material**: Rulon for low friction and ethanol compatibility.  
- **Spring preload**: Maintains sealing during initial startup, before pressure is sufficient.  
- **Pressure-actuated**: Internal pressure presses the Rulon against the shaft during operation.  
- **Bearing**: High-speed, no-lubrication bearing supports shaft alignment and reduces wear.

<img src="images/engine_pump_slice.png" alt="Pump Cross-Section" width="600"/>
<p align="center"><i>Cross-section showing pump seal, shaft, and flow path.</i></p>

---

## Cooling System

- Copper pipes routed around the chamber provide **ethanol regenerative cooling**, following early rocket engineering practices.  
- Pipes are sized to maintain fuel flow while limiting pressure drop.  
- Ethanol doubles as coolant and propellant, demonstrating efficient system integration.

---

## Key Parameters

| Parameter              | Value          | Units | Notes |
|------------------------|----------------|-------|-------|
| Chamber Pressure        | ~250           | psi   | Target operating pressure |
| Oxidizer / Fuel Ratio   | 4.7            | —     | Corrected from initial Step Zero |
| Predicted Thrust        | ~1             | N     | Small-scale educational engine |
| Theoretical Efficiency  | ~91.5          | %     | Chamber/nozzle efficiency |

---

## Engineering Lessons & Challenges

- **Step Zero Mistake**: The O/F ratio was initially flipped, causing cascading design issues in chamber sizing and injector selection.  
- **Revision 2**: Corrected the ratio and adjusted injector and nozzle parameters; however, project development paused due to moving schools and states.  
- **Pump Design**: Balancing self-acting seals, spring preload, and bearing selection provided hands-on insight into fluid mechanics and mechanical design.  
- **Learning Outcomes**: The project strengthened CAD modeling skills, understanding of combustion and fluid dynamics, and awareness of design iteration and problem-solving under constraints.

---

## References

1. MIT Rocket Team – Topic 6: Injector Design  
   https://wikis.mit.edu/confluence/display/RocketTeam/Topic+6%3A+Injector+Design  

2. Thesis on Injector & Combustion Analysis  
   https://etd.lib.metu.edu.tr/upload/12624543/index.pdf  

3. NASA Contractor Report: Pump Design for Space Propulsion  
   https://ntrs.nasa.gov/api/citations/19870008232/downloads/19870008232.pdf  

4. NASA Report on Pumps and Loads  
   https://ntrs.nasa.gov/api/citations/19950013379/downloads/19950013379.pdf  

5. Pump Seal Behavior & Materials  
   https://ntrs.nasa.gov/api/citations/19880004221/downloads/19880004221.pdf  

6. Older NASA Report on Pump Seals  
   https://ntrs.nasa.gov/api/citations/19770024556/downloads/19770024556.pdf
