#### **RISC-V SoC – VSD Tapeout Program 🚀**
This repository documents the complete RTL-to-GDSII design of a RISC-V System-on-Chip (SoC) using open-source EDA tools. The project is part of the VSD tapeout program, where top designs are selected for fabrication.

#### **📌 Design Flow Overview**
The project follows a standard VLSI design cycle to take the processor from code to a physical layout.

**RTL Design:** The processor core and its modules (ALU, Register File, etc.) are designed in Verilog.

**Functional Verification:** The design's logic is tested using Icarus Verilog for simulation and GTKWave for waveform analysis.

**Synthesis:** The Verilog RTL is converted into a gate-level netlist using Yosys.

**Physical Design:** The netlist is used by OpenLANE to perform floorplanning, placement, and routing, generating the final GDSII layout.

**Tapeout:** The final GDSII file is prepared for potential fabrication.

#### **🛠️ Tools Used**
**Design & Verification:** Verilog, Icarus Verilog, GTKWave

**Synthesis:** Yosys

**Physical Design:** OpenLANE, Magic


