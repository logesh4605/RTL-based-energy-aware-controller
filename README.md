# RTL-based-energy-aware-controller
Designed a 3-state (ACTIVE/IDLE/SLEEP) FSM controller applying clock and power gating to cut dynamic power by eliminating idle-state switching activity. Verified state transitions and gating logic via functional simulation in Vivado across all input conditions.
⚡ RTL-Based Energy Aware Controller

An RTL (Register Transfer Level) power management controller designed in Verilog HDL to reduce unnecessary power consumption by dynamically controlling the operation of a functional block using a Finite State Machine (FSM). The design demonstrates low-power digital design techniques commonly used in embedded systems and VLSI applications.

---

📌 Overview

Power optimization is one of the most important aspects of modern digital system design. This project implements an Energy Aware Controller that monitors system activity and intelligently enables or disables a functional block to minimize dynamic power consumption.

The controller transitions between ACTIVE, IDLE, and SLEEP states based on input activity. A 4-bit counter is used as the functional block to demonstrate the controller's behavior.

---

✨ Features

- ⚡ RTL implementation using Verilog HDL
- 🔄 Finite State Machine (FSM) based power management
- 💤 Automatic transition to Sleep Mode during inactivity
- 🚀 Instant wake-up on activity detection
- 🔋 Dynamic enable control for power saving
- 📈 Functional block enabled only when required
- 🧪 Simulation-ready design for FPGA/VLSI learning

---

🛠️ Design Modules

1. Energy Aware Controller

- Monitors system activity
- Controls state transitions
- Generates enable signal for the functional block

2. Functional Block

- 4-bit binary counter
- Operates only when enable signal is HIGH

3. Top Module

- Integrates the controller and functional block
- Provides the complete RTL design hierarchy

---

⚙️ FSM States

State| Description
ACTIVE| Functional block operates normally.
IDLE| Waits for activity while monitoring idle time.
SLEEP| Functional block is disabled to reduce power consumption.

State Transition

          Activity = 1
      +--------------------+
      |                    |
      ▼                    |
  +---------+         +-----------+
  | ACTIVE  | ------> |   IDLE    |
  +---------+         +-----------+
       ▲                   |
       |                   |
       | Activity=1        | Idle Timeout
       |                   ▼
       +-------------+-----------+
                     |  SLEEP    |
                     +-----------+
                           |
                     Activity = 1
                           |
                           ▼
                        ACTIVE

---

📂 Project Structure

RTL-Energy-Aware-Controller/
│
├── energy_aware_controller.v
├── functional_block.v
├── top_module.v
├── testbench.v
├── simulation_waveform.png
├── rtl_schematic.png
└── README.md

---

💻 Tools Used

- Verilog HDL
- Xilinx Vivado
- RTL Simulation
- FSM Design

---

🚀 Working Principle

1. System starts in ACTIVE state.
2. When no activity is detected, the controller enters IDLE state.
3. If inactivity continues for the specified idle count, the controller enters SLEEP state.
4. In SLEEP state, the enable signal becomes LOW, stopping the functional block.
5. Whenever new activity is detected, the controller immediately returns to ACTIVE state and resumes operation.

---

📊 Power Saving Strategy

Instead of allowing the functional block to operate continuously:

- ACTIVE → Enable = HIGH
- IDLE → Enable = HIGH
- SLEEP → Enable = LOW

Disabling the functional block during idle periods helps reduce unnecessary switching activity and lowers dynamic power consumption.

---

📁 RTL Modules

Module| Description
"energy_aware_controller.v"| FSM-based power management controller
"functional_block.v"| 4-bit counter controlled by enable signal
"top_module.v"| Top-level integration module

---

🎯 Applications

- Low-Power Digital Systems
- Embedded Controllers
- FPGA-Based Designs
- Battery-Powered Devices
- IoT Edge Devices
- VLSI Power Management
- Digital System Prototyping

---

🔮 Future Enhancements

- Clock Gating implementation
- Power Gating support
- Dynamic Voltage and Frequency Scaling (DVFS)
- Multiple functional block control
- FPGA hardware implementation
- Power consumption analysis
- ASIC implementation flow

---

📚 Technologies

- Verilog HDL
- RTL Design
- Finite State Machine (FSM)
- Digital Logic Design
- Low Power VLSI
- Embedded System Design

---

👨‍💻 Author

Logeshwaran G

Electronics and Communication Engineering (ECE)

Aspiring Embedded Systems Engineer | RTL Design | Verilog HDL | FPGA | VLSI

---

⭐ Support

If you found this project useful or learned something from it, consider giving this repository a ⭐ Star.
