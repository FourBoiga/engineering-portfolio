# High‑Pressure Liquid Rocket Engine — Ethanol / Nitrous Oxide

## Overview

This project presents the engineering design of a small, high‑pressure liquid rocket engine fueled by ethanol and nitrous oxide. The engine was designed in **Fusion 360** with attention to combustion chamber geometry, pintle injector design, nozzle performance, and practical pumping considerations.

The design emphasizes engineering reasoning, understanding of propulsion fundamentals, and CAD‑driven system integration.

---

## Design Goals

- Explore liquid rocket propulsion design using ethanol and nitrous oxide.
- Understand combustion chamber pressure, injector behavior, and nozzle expansion.
- Apply historical and technical literature to inform engineering decisions.
- Create a coherent CAD model that can support future fabrication and testing.

---

## System Architecture

The engine consists of:

- **Combustion Chamber** — sized for ~250 psi operating pressure.
- **Pintle Injector** — designed for efficient mixing of fuel and oxidizer.
- **Copper Coolant Pipes** — ethanol coolant channels inspired by early liquid engines.
- **Pump‑Fed Ethanol System** — target flow rate 0.1313 with a pressure delta of ~235 psi.
- **Pressure‑Fed Oxidizer** — nitrous oxide at 800–1000 psi to maintain liquid state without a second pump.
- **Nozzle** — optimized for ~0.9 atm exit pressure and ~1 N thrust.

### Injector & Nozzle Geometry

<img src="images/engine_injector_side.png" alt="Injector Side View" width="600"/>
<p align="center"><i>Injector sliced from the side showing flow passages and pintle geometry.</i></p>

<img src="images/engine_injector_top.png" alt="Injector Top View" width="600"/>
<p align="center"><i>Top view of the pintle injector design.</i></p>

<img src="images/engine_nozzle_injector_slice.png" alt="Nozzle & Injector Cross‑Section" width="600"/>
<p align="center"><i>Cross‑section showing nozzle and injector integration.</i></p>

<img src="images/engine_pump_slice.png" alt="Pump Cross‑Section" width="600"/>
<p align="center"><i>Cross‑section of the pump section showing fluid paths.</i></p>

<img src="images/engine_full_assembly.png" alt="Full Engine Assembly" width="600"/>
<p align="center"><i>Full CAD assembly showing overall design layout.</i></p>

---

## Key Parameters

| Parameter | Value | Units | Notes |
|-----------|-------|-------|-------|
| Chamber Pressure | ~250 | psi | Target design pressure |
| Oxidizer / Fuel Ratio | 4.7 | — | Corrected from initial Step Zero |
| Ethanol Flow Rate | 0.1313 | kg/s? | Pump specification used for design |
| Oxidizer Storage Pressure | 800–1000 | psi | Ensures nitrous remains liquid |
| Predicted Thrust | ~1 | N | Estimated for small scale educational engine |
| Target Efficiency | ~91.5 | % | Estimated nozzle/chamber efficiency |

These parameters reflect design targets based on theoretical engine sizing and pump capabilities. They are consistent with “micro‑engine” thrust levels.

---

## Engineering Insights & Challenges

### Pintle Injector Design
The pintle injector was chosen for its:

- Simplicity and ease of CAD design.
- Ability to produce a centrally directed oxidizer jet surrounded by fuel flow.
- Effective atomization for stable combustion in small engines.

### Cooling Strategy
Copper coolant pipes wrap the chamber and injector region using ethanol as the coolant. Ethanol’s water content and thermal properties help absorb heat loads near the throat, a strategy inspired by historical regenerative cooling designs prior to metal additive manufacturing.

### Pump and Flow Considerations
With only the ethanol pump being modeled, ethanol delivery is handled actively while nitrous oxide relies on pressurized storage. This **simplifies the oxidizer feed** and reduces mechanical complexity.

### CAD‑Driven Decision Making
All geometry was modeled in Fusion 360 with emphasis on:

- Manufacturability
- Fluid feed passage continuity
- Injector alignment and nozzle throat contours

Design decisions were reinforced by reviewing literature on injector design and pump seal behavior.

---

## Lessons Learned

- Fluid flow and combustion performance rely heavily on **injector geometry and mixture distribution**.
- Early decisions like O/F ratio have cascading impacts on chamber and nozzle sizing.
- **Historical design practices** (like regenerative cooling) offer valuable engineering insights even in modern CAD workflows.
- Precision CAD modeling is critical — especially when planning for future fabrication.

---

## References & Technical Sources

The following technical resources were consulted to inform design decisions, injector geometry, pump behavior, and seal considerations:

1) **MIT Rocket Team – Topic 6: Injector Design**  
   https://wikis.mit.edu/confluence/display/RocketTeam/Topic+6%3A+Injector+Design  
   *A practical guide for injector design considerations and flow patterns.*

2) **Thesis on Injector & Combustion Analysis**  
   https://etd.lib.metu.edu.tr/upload/12624543/index.pdf  
   *Detailed study of spray patterns and combustion chamber mixing.*

3) **NASA Contractor Report: Pump Design for Space Propulsion**  
   https://ntrs.nasa.gov/api/citations/19870008232/downloads/19870008232.pdf  
   *Technical guidance on designing pumps for propellant feed systems.*

4) **NASA Report on Pumps and Loads**  
   https://ntrs.nasa.gov/api/citations/19950013379/downloads/19950013379.pdf  
   *Detailed analysis on pump dynamics and pressure flow.*

5) **Pump Seal Behavior & Materials**  
   https://ntrs.nasa.gov/api/citations/19880004221/downloads/19880004221.pdf  
   *Reference on seal design and leakage behavior in high‑pressure pumps.*

6) **Older NASA Report on Pump Seals**  
   https://ntrs.nasa.gov/api/citations/19770024556/downloads/19770024556.pdf  
   *Additional context on seals under high pressure.*

---

## Final Notes

This project is a complete **engineering design exercise** documenting a liquid rocket engine from concept through detailed CAD modeling and parameter estimation. It demonstrates design depth, research integration, and propulsion fundamentals suitable for technical audiences and advanced engineering portfolios.

