# RTL to Gate-Level Simulation using Sky130 PDK

This project demonstrates how to perform RTL design, simulation, synthesis, and gate-level verification using **Icarus Verilog**, **Yosys**, and **GTKWave** with the **Sky130 HD Standard Cell Library**.

---

## 📁 Project Setup

```bash
mkdir RiscV_VSD
cd RiscV_VSD/
cd sky130RTLDesignAndSynthesisWorkshop/
cd verilog_files/
```
## 1. RTL Simulation
```bash
cd verilog_files/
iverilog good_mux.v tb_good_mux.v
./a.out
gtkwave tb_good_mux.vcd
```
#### View or edit source
```bash
gvim tb_good_mux.v -o good_mux.v
```

## 2. Synthesis Using Yosys
```bash
yosys

# Inside Yosys shell:

read_liberty -lib /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog good_mux.v
synth -top good_mux
abc -liberty /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
write_verilog good_mux_netlist.v
write_verilog -noattr good_mux_netlist.v
```

#### Open Generated Netlist
```bash
gvim good_mux_netlist.v
```

## 3. Gate-Level Simulation
```bash
iverilog \
  /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/primitives.v \
  /home/praful/RiscV_VSD/sky130RTLDesignAndSynthesisWorkshop/my_lib/verilog_model/sky130_fd_sc_hd.v \
  ternary_operator_mux_netlist.v \
  tb_ternary_operator_mux.v

./a.out
gtkwave tb_ternary_operator_mux.vcd
```
## Images for reference
## 📷 Simulation & Synthesis Outputs
## 🧪 Gate-Level Simulation
<img src="images_w1/GLS_gtk_tenary_operator.png" alt="GLS GTK Ternary Operator" width="800">

## 📜 Netlist View
<img src="images_w1/good_mux_netlist.png" alt="Good Mux Netlist" width="800">

## 📊 GTKWave Simulation
<img src="images_w1/gtk_bad_mux.png" alt="GTKWave Bad Mux" width="800">
<img src="images_w1/gtkwave_good_mux.png" alt="GTKWave Good Mux" width="800">
<img src="images_w1/gtkwave_tenary_operator_mux.png" alt="GTKWave Ternary Operator Mux" width="800">

## ✍️ Code Editing
<img src="images_w1/gvim_good_mux.png" alt="GVim Good Mux" width="800">

## ⚙️ Yosys Synthesis Results
<img src="images_w1/yosys_good_mux.png" alt="Yosys Good Mux Synthesis" width="800">
<img src="images_w1/yosys_ternary_operator_mux.png" alt="Yosys Ternary Operator Mux Synthesis" width="800">




