# RISC-V SoC – VSD Tapeout Program 🚀

This repository documents the **complete RTL-to-GDSII design** of a RISC-V System-on-Chip (SoC) using open-source EDA tools.  
The project is part of the **VSD tapeout program**, where top-performing designs are selected for fabrication.

---

## 📌 Design Flow Overview

The project follows a standard VLSI design cycle, taking the processor from code to a physical layout:

1. **RTL Design:**  
   The processor core and modules (ALU, Register File, Memory Interface, etc.) are designed in Verilog.

2. **Functional Verification:**  
   Logic is tested using **Icarus Verilog** for simulation and **GTKWave** for waveform analysis.

3. **Synthesis:**  
   Verilog RTL is converted into a gate-level netlist using **Yosys**.

4. **Physical Design:**  
   The netlist is used by **OpenLANE** for floorplanning, placement, and routing, generating the final **GDSII layout**.

5. **Tapeout:**  
   The final GDSII is prepared for potential fabrication for selected top-performing designs.

---

## 🛠️ Tools Used

| Stage                  | Tools                                |
|------------------------|--------------------------------------|
| Design & Verification  | Verilog, Icarus Verilog, GTKWave     |
| Synthesis              | Yosys                                 |
| Physical Design        | OpenLANE, Magic                       |

---



