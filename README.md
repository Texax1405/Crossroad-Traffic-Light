# 🚦 Crossroad Traffic Light Controller (Verilog HDL)

[cite_start]A functional traffic light management system designed for a four-way intersection using Verilog HDL[cite: 4, 23]. [cite_start]This project was developed as an assignment for the **Digital Design with HDL** course at **Ho Chi Minh City University of Technology (HCMUT)**[cite: 1, 3].

## 🌟 Highlights
* [cite_start]**Hierarchical Design**: Structured into manageable modules for easier debugging and integration[cite: 31, 32].
* [cite_start]**Emergency Handling**: Specialized logic to prioritize specific directions during emergency situations (`emer1`, `emer2`)[cite: 49, 50].
* [cite_start]**Countdown Display**: Integrated 7-segment display logic to show real-time countdown for traffic participants[cite: 51, 351].
* [cite_start]**State Machine Logic**: Robust Finite State Machine (FSM) implementation to manage complex light sequences[cite: 36, 552].

## ℹ️ Overview
[cite_start]The system controls two sets of traffic lights (TFL1 and TFL2) at a crossroad[cite: 23, 90]. 
* **Normal Mode Timing**: 
    * [cite_start]Green: 3 seconds[cite: 239].
    * [cite_start]Yellow: 3 seconds[cite: 239].
    * [cite_start]Red: 6 seconds[cite: 239].
* [cite_start]**Target Hardware**: Designed for FPGA boards, specifically optimized for the **Arty-7**[cite: 22].

## 🛠️ System Architecture
[cite_start]The project follows a modular hierarchical approach[cite: 31]:
* [cite_start]`TopModule.v`: The main wrapper connecting all components[cite: 98].
* [cite_start]`state_of_light.v`: Controls the global state (Normal vs. Emergency)[cite: 142, 143].
* [cite_start]`traffic_light_1.v` & `traffic_light_2.v`: Manage individual light sequences and local counters[cite: 218, 288].
* [cite_start]`seven_segment_display.v`: Converts binary counters into 7-segment LED signals[cite: 350, 351].

## 🚀 Getting Started

### 1. Requirements
* [cite_start]**Software**: Xilinx Vivado Design Suite[cite: 22].
* [cite_start]**Language**: Verilog HDL[cite: 24].

### 2. How to Install Vivado
To run the simulations or synthesize the code:
1.  Go to the [Xilinx Vivado Official Page](https://www.xilinx.com/products/design-tools/vivado.html).
2.  Download the **Vivado ML Standard Edition** (Free version).
3.  [cite_start]During installation, ensure the **Artix-7** device support is selected to match the project requirements[cite: 22].

### 3. Simulation & Testing
[cite_start]To verify the design, a testbench (`tb_TopModule.v`) is provided[cite: 457]. [cite_start]Run the **Behavioral Simulation** in Vivado to see the waveforms[cite: 35, 38].

## 🧪 Test Cases
| Scenario | Inputs | Expected Result |
| :--- | :--- | :--- |
| **Normal Cycle** | `rst=0`, `emer1=0`, `emer2=0` | [cite_start]Lights cycle Green -> Yellow -> Red[cite: 259, 329]. |
| **Emergency 1** | `emer1=1`, `emer2=0` | [cite_start]Light 1 stays **Green**, Light 2 stays **Red**[cite: 546]. |
| **Emergency 2** | `emer1=0`, `emer2=1` | [cite_start]Light 2 stays **Green**, Light 1 stays **Red**[cite: 547]. |
| **Collision Prevention**| `emer1=1`, `emer2=1` | [cite_start]Both lights stay **Green** then turn off for safety[cite: 548]. |
| **Reset** | `rst=1` | [cite_start]All displays and lights turn **Off**[cite: 309, 325]. |

## ✍️ Authors
* [cite_start]**Tran Minh Tuong** - 2353304 [cite: 8]
* [cite_start]**Nguyen Hieu Trung** - 2353244 [cite: 8]
* [cite_start]**Ho Ngoc Quynh Anh** - 2352033 [cite: 8]
* [cite_start]**Phuong Xuong Duc** - 2352270 [cite: 8]
* [cite_start]**Pham Minh Nhat** - 2352863 [cite: 8]
* [cite_start]**Lecturer**: Nguyen Thanh Loc [cite: 5]

---
[cite_start]© 2026 HCMUT - Faculty of Computer Science and Engineering[cite: 1, 11].