# Week 0: Repository & Tool Setup

### **Objective**

The goal of this week was to prepare my system for the program by setting up the required Linux/Ubuntu environment and installing the foundational EDA tools. This is a critical step to ensure I am ready for the Inauguration Call on September 18th and the subsequent weekly tasks.

---

### **System Setup**

I have chosen to set up a virtual machine on my Windows system to run the Linux environment, following the program's guidelines.

-   **Virtualization Software:** Oracle VirtualBox
    -   <https://www.virtualbox.org/wiki/Downloads>
-   **Operating System:** Ubuntu 22.04 LTS
-   **Virtual Machine Configuration:**
    -   **RAM:** 6 GB
    -   **HDD:** 50 GB
    -   **vCPU:** 4

---

### **Tool Installation & Verification**

I successfully installed the core open-source EDA tools required for the initial training phase. Below are the steps I followed and the verification screenshots.

#### **1. Yosys (Synthesis)**

I followed the build steps from the Yosys GitHub repository.

```bash
$sudo apt-get update$ git clone [https://github.com/YosysHQ/yosys.git](https://github.com/YosysHQ/yosys.git)
$ cd yosys
$ sudo apt install make
$ sudo apt-get install build-essential clang bison flex \
 libreadline-dev gawk tcl-dev libffi-dev git \
 graphviz xdot pkg-config python3 libboost-system-dev \
 libboost-python-dev libboost-filesystem-dev zlib1g-dev
$make config-gcc$ make
$ sudo make install
