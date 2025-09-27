## Incomplete and Complete Case Statements with Sky130
This project demonstrates the simulation and synthesis of incomplete and complete case statements, including bad case handling, using Icarus Verilog, Yosys, and GTKWave with the Sky130 HD Standard Cell Library.

## 1. Incomplete If Statement (incomp_if.v)
### RTL Simulation
```bash
iverilog incomp_if.v tb_incomp_if.v./a.outgtkwave tb_incomp_if.vcd
Synthesis
yosysread_verilog incomp_if.vsynth -top incomp_ifshow
```
### 📷 Outputs


### GTKWave Simulation: <img src="images/incomp_if_gtkwave.png" alt="incomp_if GTKWave" width="800">

### Yosys Synthesis Result: <img src="images/incomp_if_yosys.png" alt="incomp_if Yosys" width="800">



## 2. Incomplete If-Else Statement (incomp_if2.v)
### RTL Simulation
```bash
iverilog incomp_if2.v tb_incomp_if2.v./a.outgtkwave tb_incomp_if2.vcd
Synthesis
yosysread_verilog incomp_if2.vsynth -top incomp_if2abc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.libshow
```
### 📷 Outputs

### GTKWave Simulation: <img src="images/incomp_if2_gtkwave.png" alt="incomp_if2 GTKWave" width="800">

### Yosys Synthesis Result: <img src="images/incomp_if2_yosys.png" alt="incomp_if2 Yosys" width="800">


## 3. Incomplete Case Statement (incomp_case.v)
### RTL Simulation
```bash
iverilog incomp_case.v tb_incomp_case.v./a.outgtkwave tb_incomp_case.vcd
Synthesis
yosysread_verilog incomp_case.vsynth -top incomp_caseabc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.libshow
```
### 📷 Outputs

### GTKWave Simulation: <img src="images/incomp_case_gtkwave.png" alt="incomp_case GTKWave" width="800">

### Yosys Synthesis Result: <img src="images/incomp_case_yosys.png" alt="incomp_case Yosys" width="800">



## 4. Complete Case Statement (comp_case.v)
### RTL Simulation
```bash
iverilog comp_case.v tb_comp_case.v./a.outgtkwave tb_comp_case.vcd
Synthesis
yosysread_verilog comp_case.vsynth -top comp_caseabc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.libshow
```
### 📷 Outputs


### Yosys Synthesis Result: <img src="images/comp_case_yosys.png" alt="comp_case Yosys" width="800">


## 5. Bad Case Statement (bad_case.v)
### RTL Simulation
```bash
iverilog bad_case.v tb_bad_case.v./a.outgtkwave tb_bad_case.vcd
Synthesis and Netlist Generation
yosysread_verilog bad_case.vsynth -top bad_caseabc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.libwrite_verilog -noattr bad_case_net.vshow
```
### Gate-Level Simulation
```bash
iverilog /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/primitives.v \/home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/sky130_fd_sc_hd.v \bad_case_net.v tb_bad_case.v./a.outgtkwave tb_bad_case.vcd
```
### 📷 Outputs

### GTKWave Simulation: <img src="images/bad_case_gtkwave.png" alt="bad_case GTKWave" width="800">

### Yosys Synthesis Result: <img src="images/bad_case_yosys.png" alt="bad_case Yosys" width="800">
### Netlist View (no attributes): <img src="images/bad_case_noattr_yosys.png" alt="bad_case No Attributes Yosys" width="800">


`
