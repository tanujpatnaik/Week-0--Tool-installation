# Week-0  (Tool-installation)
<details>
<summary> Task-1 - Lecture Summary </summary>
  
# Digital Vlsi SOC design and Planning
  
## Application Development and Compilation
* Start with an application in C language.
* Verify correctness using a standard compiler (e.g., gcc, riscv-gcc, arm-gcc).
* Measure and analyze the output of the compiled program.
* Model the specifications of the application in a C-like format and re-check correctness.

## RTL Hardware Description
* Write the soft copy of hardware in Verilog (RTL).
* Reuse the same application to run on the designed hardware for functional verification.
* RTL design is divided into:
*  1) Processor (synthesizable), 
*  2) Peripherals / IPs
(Macros: Reusable and synthesizable blocks.)
(Analog IPs: Handle naturally occurring analog signals.
Used for signal conversion, frequency scaling, etc.
Written as functional RTL but not synthesizable, since they map directly to MOSFET-based circuits.)

## SoC Integration
* A SoC Engineer connects the processor, peripherals, and IPs with GPIOs.
* Run the same application on the SoC for verification.
* Processor integrated with macros and analog IPs is referred to as a Microcontroller.

## Physical Design (PD) Flow
* Convert RTL to GDSII format.
* Perform physical checks:
DRC (Design Rule Check),
LVS (Layout vs. Schematic)
* Send GDSII to the foundry (Tapeout).
* Fabricated chip is received from foundry (Tapein).

## Board Bring-Up and System Verification
* Prepare a board with the fabricated chip, memory, and peripherals.
* Run the original C application again to verify system functionality.
* Once verified, the design can be deployed in real-world applications like:
Arduino boards,
Smartwatches,
Embedded IoT systems.

<img width="1765" height="957" alt="Screenshot 2025-09-20 142411" src="https://github.com/user-attachments/assets/ad51aa8c-f57a-4ed9-81a4-c6996a91ba2d" />

</details>



<details>
	<summary>Task-2 - Tools Installation </summary>

# System Check 
* 8GB RAM, 50 GB HDD 
* Ubuntu 20.04+ 
* 4vCPU
	
# Tools Installation
## Yosys
```
$ sudo apt-get update 
$ git clone https://github.com/YosysHQ/yosys.git 
$ cd yosys 
$ sudo apt install make (If make is not installed please install it)  
$ sudo apt-get install build-essential clang bison flex \ 
libreadline-dev gawk tcl-dev libffi-dev git \ 
graphviz xdot pkg-config python3 libboost-system-dev \ 
libboost-python-dev libboost-filesystem-dev zlib1g-dev 
$ make config-gcc
$ make  
$ sudo make install 
```
![yo](https://github.com/user-attachments/assets/316864fd-1dfc-4278-a8d4-10741e47ba97)

## Iverilog
```
sudo apt-get update 
sudo apt-get install iverilog 
```
![iv](https://github.com/user-attachments/assets/be5028d8-f1a8-4017-952d-7f9135de2830)


## GTKWave
```
sudo apt-get update 
sudo apt install gtkwave
```

![gtk](https://github.com/user-attachments/assets/00c68fe7-217f-421d-8dae-05a147e353f0)
## ngspice
```
$ tar -zxvf ngspice-37.tar.gz 
$ cd ngspice-37 
$ mkdir release 
$ cd release 
$ ../configure  --with-x --with-readline=yes --disable-debug 
$ make 
$ sudo make install
```
![ng](https://github.com/user-attachments/assets/5ab4f617-b338-49e8-bcc1-a33b8276bb55)

## magic
```
$   sudo apt-get install m4 
$   sudo apt-get install tcsh 
$   sudo apt-get install csh 
$   sudo apt-get install libx11-dev
$   sudo apt-get install tcl-dev tk-dev 
$   sudo apt-get install libcairo2-dev 
$   sudo apt-get install mesa-common-dev libglu1-mesa-dev 
$   sudo apt-get install libncurses-dev 
```
![magic](https://github.com/user-attachments/assets/d7f1b657-c652-4b12-8779-a111f6b40344)

</details>
