# 6 GHz Microstrip Bandpass Filter Prototype

This repository contains the simulation environment and design files for a **6 GHz High-Q Microstrip Bandpass Filter** designed for a high-performance 2-layer RF PCB prototype using a genuine **Rogers R4003C** core material.

The primary goal of this project is to model, optimize, and compare high-frequency electromagnetic simulations with real-world Vector Network Analyzer (VNA) measurements to study manufacturing tolerances and numerical modeling accuracy.

---

## Technical Specifications

| Parameter | Specification | Notes |
| :--- | :--- | :--- |
| **Center Frequency ($f_0$)** | 6.2 GHz – 6.4 GHz | Target ISM/WiFi 6E Band |
| **Passband Ripple** | < 0.5 dB | Optimized input tapping |
| **Substrate Core** | Rogers R4003C | Strict 0.254 mm (10 mil) thickness |
| **Dielectric Constant ($\epsilon_r$)** | 3.55 | Stable across high frequencies |
| **Loss Tangent ($\tan\delta$)** | 0.0027 | Ultra-low dissipation factor |
| **Layer Count** | 2 Layers | Solid back-side ground plane |
| **Copper Weight** | 1 oz (0.035 mm) | Finished top/bottom copper |

---

## Stackup Architecture

To eliminate expensive hybrid lamination setup fees and minimize prototyping costs, the layout uses a single-core, 2-layer microstrip configuration:

* **Top Copper (L1):** Filter finger elements, coupled resonators, and 50 $\Omega$ feedlines ($0.035\text{ mm}$ finished thickness).
* **Dielectric Core:** 0.254 mm (10 mil) Rogers R4003C core substrate.
* **Bottom Copper (L2):** Continuous, uninterrupted RF ground return plane ($0.035\text{ mm}$ finished thickness).

---

## Simulation Results

The simulation environment uses `gerber2ems` as an automated Python parsing interface alongside **OpenEMS** for Finite-Difference Time-Domain (FDTD) full-wave electromagnetic analysis.

### S-Parameter Analysis ($S_{11}$ and $S_{21}$)
The insertion loss ($S_{21}$) demonstrates sharp roll-off characteristics bounding the target passband. The return loss ($S_{11}$) stays deeply notched within the operational band, ensuring maximum power transfer.

![](./plots/S_x1.png)

### Impedance & Smith Chart Matching
The input tap points on the outer resonator fingers have been finely tuned to transform the edge resonances directly into the center 50 $\Omega$ characteristic impedance locus of the network.

![](./plots/S_11_smith.png)

---

## How to Run the Simulations

### Prerequisites
Ensure you have an active Python virtual environment with `gerber2ems` installed, alongside a working installation of `OpenEMS`.

```bash
# Activate your virtual environment
source venv/bin/activate

# Verify your configuration and dependencies
gerber2ems --help
