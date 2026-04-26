# DGPE – Digital Grating Percolation Engine

## Overview
A **comparator-free**, **deterministic-latency** Top‑K selection accelerator for FPGA.  
Built with AMD Vitis HLS, targeting Xilinx Zynq‑7000 (XC7Z020CLG400‑1).

Unlike traditional sorting networks, DGPE uses a physics-inspired **multi‑level percolation** mechanism with **adaptive threshold relaxation** to filter out low‑score elements without expensive comparator trees.

## Key Features
- Comparator‑free architecture (no bitonic sorters, no wide comparators)
- Deterministic latency: same cycle count regardless of data distribution
- Streaming‑friendly: II=1 pipeline, 8‑way parallel scan
- Ultra‑low FPGA resource footprint
- Self‑contained IP with AXI‑Stream input and AXI‑Lite control

## Performance (Post‑Implementation on XC7Z020‑1)
| Metric | Value |
|--------|-------|
| Max Frequency | 171.94 MHz |
| LUTs | 1,202 (2.26%) |
| FFs | 1,083 (1.01%) |
| BRAMs | 32 |
| Hard Latency (N=1000, K=10) | 129.5 µs |
| Post‑Route WNS | 2.284 ns |

## Speedup vs ARM Cortex‑A9 @ 667 MHz
| Data Distribution | DGPE Hardware | ARM Estimate | Speedup |
|-------------------|---------------|-------------|---------|
| Uniform | 129.5 µs | 930 µs | **7.18×** |
| Zipf | 129.5 µs | 795 µs | **6.14×** |
| Constant | 129.5 µs | 528 µs | **4.08×** |

## Verification Status
- [x] C Simulation
- [x] C Synthesis (171.94 MHz)
- [x] C/RTL Co‑simulation
- [x] Place & Route (Timing Met: WNS = 2.284 ns)
- [ ] On‑board test (planned)

## Repository Structure
| Folder | Content |
|--------|---------|
| `benchmark/` | C simulation output logs |
| `docs/` | Implementation reports and screenshots |

## IP Access
The full HLS source is not publicly disclosed at this stage.  
For academic collaboration or commercial licensing, please open a GitHub Issue or Discussion in this repository.

## Author
**[Karsen]** – Self‑directed research project.  
Interested in FPGA acceleration, computer architecture, and hardware‑software co‑design.
