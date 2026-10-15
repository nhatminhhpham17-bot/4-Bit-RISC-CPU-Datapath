# 4-Bit RISC CPU Datapath (3-Stage Pipeline)

##  Project Overview
This project implements a custom 4-bit RISC CPU featuring a 3-Stage Pipeline architecture (Instruction Fetch, Decode, Execute) based on the Harvard memory model. The design is mapped and physically implemented on the **Artix-7 FPGA** using Vivado 2026.1.

##  Custom Hardware Upgrades
- **Early Branch Mechanism:** Relocated the Unconditional Jump (JMP) logic directly into the Decode (ID) stage, successfully reducing the branch penalty to just 1 clock cycle.
- **Advanced Flag Detection:** Upgraded the Execute stage ALU to accurately detect and assert Negative (N) and Overflow (V) flags for signed arithmetic operations.
- **Logical Shift Left (SHL):** Expanded the datapath control by implementing a dedicated hardware-level SHL instruction using opcode `1100`.

##  Synthesis & Implementation Results
The logic optimization and hardware synthesis completely preserved the pipeline hierarchy using physical attributes (`DONT_TOUCH` / `KEEP_HIERARCHY`), yielding the following efficient footprint:
- **Hardware Utilization:** 66 Slice LUTs, 60 Slice Registers (FFs), 4 LUTRAMs, 30 IOs.
- **Power Consumption:** 4.528 W Total On-Chip Power (Junction Temp: 47.6°C).
- **Verification:** Successfully passed 100% of the top-level automated self-checking testbench (41 of 41 checks OK with zero unknown states).

##  Repository Contents
- `4bit_RISC_CPU_Pipeline.zip`: The complete archived Vivado 2026.1 project, including all RTL Verilog modules, pipeline registers, self-checking testbenches, and `.mem` files.
- `Project_Presentation.pptx`: The official project defense slide deck containing elaborated schematics, waveforms, and power reports.

---
**Author:** Pham Xuan Nhat Minh (Roll Number: HE200288)  
**Institution:** FPT University
