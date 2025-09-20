# Week 0: Repository & Tool Setup

### **Objective**

The goal of this week was to prepare my system for the program by setting up the required Linux/Ubuntu environment and installing the foundational EDA tools. 

---

### **System Setup**  
### **Recommended**
-   **Virtualization Software:** Oracle VirtualBox
    -   <https://www.virtualbox.org/wiki/Downloads>
-   **Operating System:** Ubuntu 22.04 LTS
     -   <https://ubuntu.com/download/desktop>
-   **Virtual Machine Configuration:**
    -   **RAM:** 6 GB
    -   **HDD:** 50 GB
    -   **vCPU:** 4

### **OR**

I am using **Windows Subsystem for Linux (WSL)** to run the required Linux/Ubuntu environment natively on my Windows system. This provides a lightweight and efficient alternative to a traditional virtual machine, with the full functionality of a Linux command-line interface.

* **Operating System:** Ubuntu 22.04 LTS on WSL2
* **System Resources:** I have confirmed that my system meets the program's minimum requirements (6GB RAM, 50GB HDD, 4vCPU).

---

### **Tool Installation & Verification**

I successfully installed the core open-source EDA tools required for the initial training phase. Below are the steps I followed and the verification screenshots, all performed within my WSL terminal.

#### **1. Yosys (Synthesis)**

I followed the build steps from the Yosys GitHub repository. This tool converts RTL code into a gate-level netlist.

```bash
# Update package lists
$ sudo apt-get update

# Download the Yosys source code
$ git clone [https://github.com/YosysHQ/yosys.git](https://github.com/YosysHQ/yosys.git)
$ cd yosys
$ git submodule update --init

# Install build dependencies
$ sudo apt-get install build-essential clang bison flex \
 libreadline-dev gawk tcl-dev libffi-dev git \
 graphviz xdot pkg-config python3 libboost-system-dev \
 libboost-python-dev libboost-filesystem-dev zlib1g-dev

# Compile and install the tool
$ make config-gcc
$ make
$ sudo make install
```
#### **Verification Yosys tool install**

  I ran the command to check the version and confirm a successful installation
  ``` bash
  $ yosys -V
```
![Yosys Installation Verification Screenshot](./screenshots/yosys_verify.png)

### **2. Icarus Verilog (Iverilog)**

I used the `apt-get` package manager for a straightforward installation. This is an open-source Verilog compiler and simulator.

```bash
# Update package lists
$ sudo apt-get update

# Install the tool
$ sudo apt-get install iverilog
```

#### **Verification Iverilog tool install**

I ran the command to check the version and confirm a successful installation.

```bash
$ iverilog -V
```
![Iverilog Installation Verification Screenshot](./screenshots/iverilog_verify.png)

-----

### **3. GTKWave (Waveform Viewer)**

This tool was also installed using `apt-get`. It is essential for visualizing simulation results.

```bash
# Update package lists
$ sudo apt-get update

# Install the tool
$ sudo apt-get install gtkwave
```

#### **Verification GTKWave tool install**

I ran the command to check the version and confirm a successful installation.

```bash
$ gtkwave --version
```
![GTKWave Installation Verification Screenshot](./screenshots/gtkwave_verify.png) 

----  

## Week 0: Tool Setup Summary

Here is a summary of the tools installed and verified during Week 0 of the program.

| Tool | Use / Purpose | Status |
| :--- | :--- | :--- |
| **Yosys** | Synthesizes RTL code into a gate-level netlist. | Installed & Verified ✅ |
| **Iverilog** | Compiles and simulates Verilog code. | Installed & Verified ✅ |
| **GTKWave** | Visualizes and analyzes simulation waveforms. | Installed & Verified ✅ |
