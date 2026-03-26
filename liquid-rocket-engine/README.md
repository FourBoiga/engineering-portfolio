# High‑Pressure Liquid Rocket Engine — Ethanol / Nitrous Oxide

## Overview

This project documents the engineering design of a small, high‑pressure liquid rocket engine fueled by ethanol and nitrous oxide. The engine was designed in **Fusion 360**, emphasizing combustion chamber geometry, pintle injector design, nozzle performance, and practical pump integration.

It demonstrates engineering reasoning, research-backed design, and CAD-driven system integration.

---

## Design Goals

- Explore liquid rocket propulsion design using ethanol and nitrous oxide.
- Understand combustion chamber pressure, injector behavior, and nozzle expansion.
- Apply literature and historical designs to inform engineering decisions.
- Produce a coherent CAD model for future fabrication or simulation studies.

---

## System Architecture

The engine consists of:

- **Combustion Chamber** — target pressure ~250 psi.
- **Pintle Injector** — optimized for ethanol/nitrous mixing.
- **Copper Cooling Pipes** — ethanol-based cooling channels.
- **Ethanol Pump** — delivers liquid fuel to the chamber.
- **Pressurized Nitrous Oxide Tank** — maintains oxidizer in liquid state.
- **Nozzle** — designed for ~0.9 atm exit pressure and ~1 N thrust.

---

## Injector Design

The pintle injector was chosen for:

- Simple geometry for CAD modeling.
- Effective mixing and atomization of fuel and oxidizer.
- Historical precedent in early liquid engines.

<img src="images/engine_injector_side.png" alt="Injector Side View" width="600"/>
<p align="center"><i>Side view showing flow passages and pintle geometry.</i></p>

<img src="images/engine_injector_top.png" alt="Injector Top View" width="600"/>
<p align="center"><i>Top view of the pintle injector design.</i></p>

---

## Nozzle Design

Nozzle geometry was optimized for small-scale thrust with attention to:

- Expansion ratio
- Smooth internal contours
- Integration with chamber and injector

<img src="images/engine_nozzle_injector_slice.png" alt="Nozzle & Injector Cross-Section" width="600"/>
<p align="center"><i>Cross-section of nozzle and injector integration.</i></p>

---

## Pump Section

The engine uses a dedicated ethanol pump with the following parameters:

| Parameter | Value | Units | Notes |
|-----------|-------|-------|-------|
| Ethanol Flow Rate | 0.1313 | kg/s | Pump-fed ethanol |
| Pressure Delta | 235.3 | psi | Across pump |
| Operating Notes | — | — | Nitrous oxide remains pressure-fed at 800–1000 psi |

<img src="images/engine_pump_slice.png" alt="Pump Cross-Section" width="600"/>
<p align="center"><i>Cross-section of the pump showing fluid paths and feed design.</i></p>

---

## Full Assembly

The complete engine assembly shows all components integrated:

<img src="images/engine_full_assembly.png" alt="Full Engine Assembly" width="600"/>
<p align="center"><i>CAD assembly showing injector, chamber, nozzle, pump, and cooling paths.</i></p>

---

## Key Parameters

| Parameter | Value | Units | Notes |
|-----------|-------|-------|-------|
| Chamber Pressure | ~250 | psi | Target operating pressure |
| Oxidizer / Fuel Ratio | 4.7 | — | Corrected from initial Step Zero |
| Predicted Thrust | ~1 | N | Small-scale educational engine |
| Target Efficiency | ~91.5 | % | Estimated nozzle/chamber efficiency |

---

## Design Challenges & Lessons Learned

- During initial calculations, the **O/F ratio was accidentally flipped**, causing cascading design issues in chamber and injector sizing.  
- Revision 2 corrected the ratio, but project development was paused due to moving schools and states.  
- The project highlighted my **love for PCBs** and my developing understanding of pumps — a love/hate relationship with practical fluid mechanics.  
- Precision CAD modeling and reviewing historical engineering literature were essential in refining injector, nozzle, and pump designs.  
- Ethanol cooling via copper pipes demonstrated principles of regenerative cooling in small-scale engines.

---

## References

1) **MIT Rocket Team – Topic 6: Injector Design**  
   https://wikis.mit.edu/confluence/display/RocketTeam/Topic+6%3A+Injector+Design  

2) **Thesis on Injector & Combustion Analysis**  
   https://etd.lib.metu.edu.tr/upload/12624543/index.pdf  

3) **NASA Contractor Report: Pump Design for Space Propulsion**  
   https://ntrs.nasa.gov/api/citations/19870008232/downloads/19870008232.pdf  

4) **NASA Report on Pumps and Loads**  
   https://ntrs.nasa.gov/api/citations/19950013379/downloads/19950013379.pdf  

5) **Pump Seal Behavior & Materials**  
   https://ntrs.nasa.gov/api/citations/19880004221/downloads/19880004221.pdf  

6) **Older NASA Report on Pump Seals**  
   https://ntrs.nasa.gov/api/citations/19770024556/downloads/19770024556.pdf  

