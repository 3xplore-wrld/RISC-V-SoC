#### Incomplete and Complete Case Statements with Sky130
This project demonstrates the simulation and synthesis of incomplete and complete case statements, including bad case handling, using Icarus Verilog, Yosys, and GTKWave with the Sky130 HD Standard Cell Library.

#### 📁 Project Setup

Ensure the Sky130 HD Standard Cell Library is available at /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/.
Install Icarus Verilog, Yosys, and GTKWave on your system.
Clone or prepare the project directory containing the following files:
incomp_if.v, tb_incomp_if.v
incomp_if2.v, tb_incomp_if2.v
incomp_case.v, tb_incomp_case.v
comp_case.v, tb_comp_case.v
bad_case.v, tb_bad_case.v


### Ensure the Sky130 library files (primitives.v, sky130_fd_sc_hd.v) are located at /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/.


## 1. Incomplete If Statement (incomp_if.v)
## RTL Simulation
iverilog incomp_if.v tb_incomp_if.v
./a.out
gtkwave tb_incomp_if.vcd

## Synthesis
yosys
read_verilog incomp_if.v
synth -top incomp_if
show


2. Incomplete If Statement (incomp_if2.v)
RTL Simulation
iverilog incomp_if2.v tb_incomp_if2.v
./a.out
gtkwave tb_incomp_if2.vcd

Synthesis
yosys
read_verilog incomp_if2.v
synth -top incomp_if2
abc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show


3. Incomplete Case Statement (incomp_case.v)
RTL Simulation
iverilog incomp_case.v tb_incomp_case.v
./a.out
gtkwave tb_incomp_case.vcd

Synthesis
yosys
read_verilog incomp_case.v
synth -top incomp_case
abc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show


4. Complete Case Statement (comp_case.v)
RTL Simulation
iverilog comp_case.v tb_comp_case.v
./a.out
gtkwave tb_comp_case.vcd

Synthesis
yosys
read_verilog comp_case.v
synth -top comp_case
abc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show


5. Bad Case Statement (bad_case.v)
RTL Simulation
iverilog bad_case.v tb_bad_case.v
./a.out
gtkwave tb_bad_case.vcd

Synthesis and Gate-Level Simulation
yosys
read_verilog bad_case.v
synth -top bad_case
abc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
write_verilog -noattr bad_case_net.v
show

Gate-Level Simulation
iverilog /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/primitives.v /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/sky130_fd_sc_hd.v bad_case_net.v tb_bad_case.v
./a.out
gtkwave tb_bad_case.vcd


📷 Simulation & Gate-Level Outputs
1. Incomplete If Statement (incomp_if.v)

RTL Block Diagram: [Insert path to incomp_if.png]
GTKWave Simulation: [Insert path to incomp_if_gtkwave.png]

2. Incomplete If Statement (incomp_if2.v)

RTL Block Diagram: [Insert path to incomp_if2.png]
Gate-Level Netlist View: [Insert path to incomp_if2_netlist.png]
GTKWave Simulation: [Insert path to incomp_if2_gtkwave.png]

3. Incomplete Case Statement (incomp_case.v)

RTL Block Diagram: [Insert path to incomp_case.png]
Gate-Level Netlist View: [Insert path to incomp_case_netlist.png]
GTKWave Simulation: [Insert path to incomp_case_gtkwave.png]

4. Complete Case Statement (comp_case.v)

RTL Block Diagram: [Insert path to comp_case.png]
Gate-Level Netlist View: [Insert path to comp_case_netlist.png]
GTKWave Simulation: [Insert path to comp_case_gtkwave.png]

5. Bad Case Statement (bad_case.v)

RTL Block Diagram: [Insert path to bad_case.png]
Gate-Level Netlist View: [Insert path to bad_case_netlist.png]
GTKWave Simulation: [Insert path to bad_case_gtkwave.png]


Note: Replace [Insert path to ...] with actual file paths to images generated during simulation and synthesis. Ensure all paths and file names match your project directory structure.
