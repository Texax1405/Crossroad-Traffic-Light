# 🚦 Crossroad Traffic Light Controller (Verilog HDL)

A functional traffic light management system designed for a four-way intersection using Verilog HDL[cite: 4, 23]. This project was developed as an assignment for the **Digital Design with HDL** course at **Ho Chi Minh City University of Technology (HCMUT)**[cite: 1, 3].

## Highlights
* **Hierarchical Design**: Structured into manageable modules for easier debugging and integration[cite: 31, 32].
* **Emergency Handling**: Specialized logic to prioritize specific directions during emergency situations (`emer1`, `emer2`)[cite: 49, 50].
* **Countdown Display**: Integrated 7-segment display logic to show real-time countdown for traffic participants[cite: 51, 351].
* **State Machine Logic**: Robust Finite State Machine (FSM) implementation to manage complex light sequences[cite: 36, 552].

## Overview
The system controls two sets of traffic lights (TFL1 and TFL2) at a crossroad[cite: 23, 90]. 
* **Normal Mode Timing**: 
    * Green: 3 seconds[cite: 239].
    * Yellow: 3 seconds[cite: 239].
    * Red: 6 seconds[cite: 239].
* **Target Hardware**: Designed for FPGA boards, specifically optimized for the **Arty-7**[cite: 22].

## System Architecture
The project follows a modular hierarchical approach[cite: 31]:
* `TopModule.v`: The main wrapper connecting all components[cite: 98].
* `state_of_light.v`: Controls the global state (Normal vs. Emergency)[cite: 142, 143].
* `traffic_light_1.v` & `traffic_light_2.v`: Manage individual light sequences and local counters[cite: 218, 288].
* `seven_segment_display.v`: Converts binary counters into 7-segment LED signals[cite: 350, 351].

## Getting Started

### 1. Requirements
* **Software**: Xilinx Vivado Design Suite[cite: 22].
* **Language**: Verilog HDL[cite: 24].

### 2. How to Install Vivado
To run the simulations or synthesize the code:
1.  Go to the [Xilinx Vivado Official Page](https://www.xilinx.com/products/design-tools/vivado.html).
2.  Download the **Vivado ML Standard Edition** (Free version).
3.  During installation, ensure the **Artix-7** device support is selected to match the project requirements[cite: 22].

### 3. Simulation & Testing
To verify the design, a testbench (`tb_TopModule.v`) is provided[cite: 457]. Run the **Behavioral Simulation** in Vivado to see the waveforms[cite: 35, 38].

## Test Cases
| Scenario | Inputs | Expected Result |
| :--- | :--- | :--- |
| **Normal Cycle** | `rst=0`, `emer1=0`, `emer2=0` | Lights cycle Green -> Yellow -> Red[cite: 259, 329]. |
| **Emergency 1** | `emer1=1`, `emer2=0` | Light 1 stays **Green**, Light 2 stays **Red**[cite: 546]. |
| **Emergency 2** | `emer1=0`, `emer2=1` | Light 2 stays **Green**, Light 1 stays **Red**[cite: 547]. |
| **Collision Prevention**| `emer1=1`, `emer2=1` | Both lights stay **Green** then turn off for safety[cite: 548]. |
| **Reset** | `rst=1` | All displays and lights turn **Off**[cite: 309, 325]. |

## Members
* **Tran Minh Tuong** - 2353304 [cite: 8]
* **Nguyen Hieu Trung** - 2353244 [cite: 8]
* **Ho Ngoc Quynh Anh** - 2352033 [cite: 8]
* **Phuong Xuong Duc** - 2352270 [cite: 8]
* **Pham Minh Nhat** - 2352863 [cite: 8]
* **Lecturer**: Nguyen Thanh Loc [cite: 5]

---
© 2026 HCMUT - Faculty of Computer Science and Engineering[cite: 1, 11].