# Installation
1. You can install the stable versions of these open-source tools from the Ubuntu **apt** package manager.  
I am installing these tools in WSL (Windows Subsytem Linux) - Ubuntu 24.04.2 LTS.
2. Run the below commands in the terminal:
```
sudo apt update
sudo apt install -y iverilog gtkwave
```
3. Run the below commands to check whether they installed correctly by printing their version names:
```
iverilog -V
```
Prints **Icarus Verilog Parser/Elaborator version 12.0 (stable)**
```
gtkwave --version
```
or
```
gtkwave -V
```
Prints **GTKWave Analyzer v3.3.116**
# Working Commands
1. Create your RTL design and testbench modules using vim editor.
2. Add the below lines in the initial block of your testbench module:
```
$dumpfile("test.vcd");
$dumpvars(0, test);
```
You can give anyname other than **test** for the vcd file but make sure you input the same name to the GTKWave Analyzer tool command.

3. Run the below command so that the Icarus Verilog tool compiles the verilog code and generates an executable file in vvp format:
```
iverilog -o <main_module_name> <testbench_name.v> <main_design_module_name.v> <sub_design_module_name.v>
```
4. Run the below command to execute the generated vvp file and view the output in the terminal:
```
vvp <main_module_name>
```
5. Run the below command to view the simulation waveform in GTKWave Analyzer:
```
gtkwave test.vcd
```
