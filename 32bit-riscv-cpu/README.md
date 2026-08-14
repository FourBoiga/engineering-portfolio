# 32-bit RISC-V CPU (Logisim)

## Overview
This project involves the design and implementation of a custom **32-bit RISC-V processor** based on the open-source **RV32I Base Integer Instruction Set**. Built using a visual schematic editor in Logisim, the core architecture showcases gate-level hardware layout, instruction decoding, register data management, and custom datapath synchronization.

The development is divided into two phases: **Version 1 (V1)** focuses on a robust, fully verified **Single-Cycle Core Blueprint**, while **Version 2 (V2)** explores the transition into a concurrent **5-Stage Pipelined Core** (currently in the active debugging and testing phase).

---

## Architecture / Components (V1: Single-Cycle Core)
The structural layout of the single-cycle architecture utilizes discrete sub-circuits designed to execute standard RISC-V instruction formats (R-type, I-type, S-type, and B-type):

* **ALU (`riscv_alu`)**: The core execution block that computes addition, subtraction, arithmetic operations, and relational comparisons for branch execution.
* **Register File (`register_file`)**: A high-speed internal storage unit supporting 32-bit general-purpose registers. Following the RISC-V specification, register `x0` is hardwired to a constant `0` to serve as an absolute zero reference.
* **Master Control Unit (`master_control`)**: Generates single-cycle execution paths and sets the master multiplexer switches (e.g., `RegWrite`, `MemWrite`, `MemRead`, `ResultSrc`, `ALUSrc`) based on incoming instruction opcodes.
* **Immediate Generator / Decoder (`imm_decoder`)**: Extracts sign-extended immediate fields directly from incoming instructions to provide offsets for memory operations and immediate arithmetic.
* **Program Counter Unit (`pc_unit`)**: Manages the hardware instruction pointers, performing sequential execution increments (`PC + 4`) and direct branch additions for program jumps.

---

## V1 Key Features & Instruction Execution
* **32-Bit Datapath**: Every data pipeline bus, execution channel, and processing register operates at true 32-bit width.
* **Synchronous Clocking Structure**: Built with uniform global clock grids where all registers strictly update on the **rising edge** to avoid phase drifts.
* **Verified Code Loop Execution**: Successfully compiles and executes local instruction blocks. A typical diagnostic loop includes the following sequence to write, read, alter, and jump using basic instructions:
  * `ADDI x1, x0, 3` — Load 3 into x1
  * `ADDI x2, x0, 1` — Load 1 into x2
  * `SW x2, 0(x0)`   — Store the value of x2 into RAM Address 0
  * `LW x3, 0(x0)`   — Load the RAM value into x3
  * `SUB x1, x1, x3` — Perform immediate subtraction
  * `BNE x1, x0, -12` — Dynamic branch assessment to jump back to memory routines

---

## Image of the Risc-V CPU
<img src="images/Screenshot From 2026-08-14 14-20-40.png" alt="DAC PCB Top View" width="600"/>

## The Transition to V2: Pipelining Challenges & Debugging
As the project scales from a visual single-cycle layout toward a concurrent **5-Stage Pipelined Execution Core**, several critical microarchitectural bugs arose. Identifying these structural challenges highlighted the core discrepancies between static single-cycle layouts and time-multiplexed instruction streaming:

* **Structural Execution Stage Misalignment**: During early testing of the pipeline walls, data loops fell out of sync because the ALU computed math based on the un-pipelined raw register file outputs (`RD1` and `RD2`) rather than the pipelined equivalents (`RD1_EX` and `RD2_EX`), creating a permanent 1-cycle data offset.
* **Crossed Output Traps**: Mismatches in instruction decoding caused the CPU to output data on `RD1` instead of `RD2` for store operations (`SW`), disrupting standard data steering networks.
* **Data-to-Control Misalignment**: Adding structural delays showed how easily control lines can get out of phase with physical data paths, with memory writes (`MemWrite`) firing several cycles after the target address had traveled downstream. 
* **Logisim Tunnel & Bus Short-Circuits**: Visual copy-pasting of 5-bit address components (`rd`) caused shared net-name leakage, creating short-circuits across different stages. Isolating and clearing these wire fragments and rebuilding the 5-bit destination registers resolved these canvas conflicts.

---

## Future Revisions (V2 Pipelined Core)
Because the pipelined core is currently non-functional and undergoing engineering adjustments, future milestones will focus entirely on completing this high-performance upgrade:

* **Finalize the Pipelined Registers**: Lock down the structural vertical walls (`if_id_reg`, `id_ex_reg`, `ex_mem_reg`, `mem_wb_reg`) to isolate execution streams.
* **Implement Hazard & Forwarding Modules**: Wire active hazard detection logic and look-ahead stall controllers to bypass load-use conditions, eliminate simulation race conditions, and correctly tap `WriteData_EX` directly off `Forwarding MUX B`.
* **FPGA Space Optimization Strategy**: Optimize clear and reset ports by only adding reset circuitry to the 3 essential control registers (`RegWrite`, `MemWrite`, `MemRead`). This resource conservation approach saves transistor allocation on physical hardware without compromising architectural safety.
* **Migration to Verilog / SystemVerilog**: Translate the verified graphical logic canvas into modern hardware description code to prepare the RV32I microarchitecture for physical deployment and compilation onto an FPGA development board.
