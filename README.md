# Engineering Portfolio

This portfolio contains selected projects demonstrating simulation-driven design, circuit development, and applied electromagnetic theory.

---

## Projects

### 6 GHz Antenna with 6 GHz Bandpass Filter

Design and simulation of a high-frequency antenna system using electromagnetic theory and transmission line principles. The project includes impedance matching, radiation pattern analysis, and wave propagation visualization.

Key highlights:

* -35 dB S11 (excellent impedance matching)
* ~50 Ω input impedance
* 15 dBi directivity
* 91% aperture efficiency
* Full EM simulation using openEMS

→ [View Project](rf-antenna-6ghz/README.md)

---

### Portable DAC for Earbuds

Design of a compact digital-to-analog converter optimized for earbuds, focusing on low noise, signal integrity, and real-world audio performance.

Key highlights:

* Designed for high-sensitivity audio devices
* Emphasis on low noise and clean output
* Includes filtering and buffering stages
* System-level signal chain design
* Optimized for earbuds (in-ear monitors)

→ [View Project](dac-system/README.md)

---

### 50–800 MHz Software Defined Radio (SDR)

Design of a custom wideband software-defined radio covering the VHF and UHF spectrum using a modular RF front-end and FPGA-based digital signal processing.

Key highlights:

* 50–800 MHz receive coverage
* Switched RF bandpass filter bank architecture
* Low-noise amplifier and I/Q receiver design
* Custom local oscillator and PLL synthesizer development
* FPGA-based digital signal processing pipeline
* Emphasis on dynamic range, phase noise, and RF system integration

Focus areas:

* RF engineering
* Analog circuit design
* Signal integrity
* FPGA development
* Digital signal processing
* Communication systems

→ [View Project](wideband-sdr/README.md)

---

### 32-bit RISC-V CPU

Design and implementation of a 32-bit RISC-V processor architecture, moving from visual schematic design to industry-standard hardware description languages.

Key highlights:

* Implements the RV32I base integer instruction set
* Designed using a pipelined architecture with hazard detection and forwarding paths
* Developed and verified using Verilog/SystemVerilog simulation environments
* Demonstrates advanced understanding of computer microarchitecture, instruction decoding, and memory interfaces

→ [View Project](32bit-riscv-cpu/README.md)

---

### 16-bit CPU (Logisim)

Design and implementation of a 16-bit processor built from fundamental logic components, including an ALU, registers, and control unit.

Key highlights:

* Built from basic logic gates and sequential circuits
* Custom instruction execution
* Full datapath and control design
* Demonstrates understanding of computer architecture

→ [View Project](16bit-cpu/README.md)

---

### Ethanol / Nitrous Oxide Liquid Rocket Engine

Design and analysis of a small-scale bipropellant liquid rocket engine, including combustion chamber, regenerative cooling, turbopump systems, and nozzle geometry.

Focus areas:

* Fluid dynamics
* Thermodynamics
* Combustion
* Turbomachinery
* Heat transfer
* System integration

→ [View Project](liquid-rocket-engine/README.md)

---

## Engineering Approach

My approach to engineering emphasizes:

* Understanding underlying physics before simulation
* Using simulation as a validation tool, not a starting point
* Designing systems with attention to real-world constraints
* Iterating based on both theoretical and practical considerations

---

## Tools and Technologies

* **Hardware Description / Logic:** Verilog/SystemVerilog, Logisim
* **Programming:** C, Python
* **PCB Design & EDA:** KiCad, Sonnet Lite
* **Electromagnetics & Physics Simulation:** openEMS, OpenFOAM, ANSYS, RPA (Rocket Propulsion Analysis)
* **Mechanical CAD:** Fusion 360

---

## Current Focus

* RF system design and software-defined radio development
* PCB implementation of high-frequency circuits
* FPGA-based digital signal processing
* Expanding into measured validation of simulated systems
* Bare-metal embedded C programming
* Pump-fed liquid rocket propulsion systems
