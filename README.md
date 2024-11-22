# 32Bit-ALU_Synthesis

## Aim:

Synthesize 32 Bit ALU design using Constraints and analyse area and Power reports.

## Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

Synthesis: Genus

### Step 1: Getting Started

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)

### Step 2 : Performing Synthesis

The Liberty files are present in the library path,

• The Available technology nodes are 180nm ,90nm and 45nm.

• In the terminal, initialise the tools with the following commands if a new terminal is being
used.

◦ csh

◦ source /cadence/install/cshrc

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.
# PROGRAM

read_libs /cadence/install/FOUNDRY-01/digital/90nm/dig/lib/slow.lib
read_hdl alu_32bit.v
elaborate
read_sdc input_constraints.sdc 
syn_generic
report_area
syn_map
report_area
syn_opt
report_area 
report_area > alu_32bit_area.txt
report_power > alu_32bit_power.txt
write_hdl > alu_32bit_netlist.v
gui_show
# PROGRAM


#### Synthesis RTL Schematic :
![Screenshot (111)](https://github.com/user-attachments/assets/505b180a-76a0-4046-a5cb-51cb1126c504)

#### Area report:
![Screenshot (114)](https://github.com/user-attachments/assets/c8def240-a4d9-4194-b678-fd785cb3ca18)

#### Power Report:
![Screenshot (115)](https://github.com/user-attachments/assets/79f12dfd-b9ae-456e-b704-e9e890fdaa21)

#### Result: 

The generic netlist of 32 bit ALU  has been created, and area, power reports have been tabulated and generated using Genus.
