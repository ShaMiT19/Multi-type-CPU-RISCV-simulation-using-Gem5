# Multi-Type CPU RISC-V Simulation using Gem5

## Table of Contents
- [Introduction](#introduction)
- [Project Overview](#project-overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Simulation Types](#simulation-types)
- [Benchmarking](#benchmarking)
- [CPU Models](#cpu-models)
- [Performance Analysis](#performance-analysis)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Introduction
This project focuses on simulating multi-type CPU processors using the Gem5 simulator, with a specific emphasis on RISC-V architectures. Gem5 is a highly modular and configurable platform that allows for detailed emulation of complex processor architectures. Our study explores various multi-core configurations to analyze performance metrics under different scenarios.

## Project Overview
The main objectives of this project are:
- Implement functional and cycle-accurate models for RISC-V processors
- Analyze performance across different CPU types, cache hierarchies, and interconnect networks
- Integrate and evaluate custom benchmarking suites, particularly the Ligra benchmark
- Provide insights into multi-core architecture performance and potential optimization areas

## Prerequisites
- Gem5 simulator (latest version)
- RISC-V toolchain
- Python 3.x
- GCC/G++ compiler
- Make

## Installation
# Clone Gem5
git clone https://gem5.googlesource.com/public/gem5

# Build Gem5 for RISC-V
cd gem5
scons build/RISCV/gem5.opt -j$(nproc)

# Install the RISC-V toolchain
# Instructions may vary based on your operating system
# For Ubuntu:
sudo apt-get install gcc-riscv64-linux-gnu

# Clone this project repository
git clone https://github.com/your-username/multi-type-cpu-riscv-sim.git

# Usage
# 1. Navigate to the project directory
cd multi-type-cpu-riscv-sim

# 2. Compile the Ligra benchmark
cd Ligra/apps
make

# 3. Run a simulation
./run_simulation.sh <cpu_type> <benchmark> <dataset>

Replace `<cpu_type>`, `<benchmark>`, and `<dataset>` with your desired options.

## Simulation Types
Our project supports two main simulation styles:

1. **Functional Level Simulation**
- Pros: High-speed simulation, quick application functionality verification
- Cons: Lacks micro-architectural details, no timing accuracy

2. **Cycle-Accurate Simulation**
- Pros: Detailed performance insights, accurate timing information
- Cons: Slower simulation speed

## Benchmarking
We primarily use the Ligra benchmark suite for evaluating processor performance. Ligra is a lightweight graph processing framework designed for shared memory systems. It allows us to analyze:
- Cache behavior
- Scalability
- Overall system performance under diverse workloads

## CPU Models
The project supports various CPU models, including:
- AtomicSimpleCPU
- DerivO3CPU
- NonCachingSimpleCPU
- O3CPU
- RiscvMinorCPU

Each model has distinct characteristics and performance trade-offs.

## Performance Analysis
We analyze several key performance metrics:
- Simulated Time
- Host Time
- Host Tick Rate
- Host Instruction Rate
- Cycles Per Instruction (CPI)
- Instructions Per Cycle (IPC)
- Number of CPU Cycles
- Number of Instructions

## Results
Our simulations revealed significant differences between CPU architectures:
- AtomicSimpleCPU achieved a Host Instruction Rate of 1,464,612 instructions per second and an IPC of 0.830
- DerivO3CPU and O3CPU demonstrated higher efficiencies with IPCs of 1.487 and Host Instruction Rates of 253,238 and 265,901, respectively
- Simulated Time was consistent at 0.001093 seconds for DerivO3CPU and O3CPU, outperforming AtomicSimpleCPU's 0.001958 seconds

These results highlight the performance trade-offs among CPU types, with simpler models prioritizing simplicity over efficiency, while more complex models showcase advanced pipeline optimizations for improved execution rates.

## Contributing
We welcome contributions to this project. Please follow these steps:
1. Fork the repository
2. Create a new branch for your feature
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.
