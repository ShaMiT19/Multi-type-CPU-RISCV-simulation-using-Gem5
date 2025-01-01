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
1. Clone the Gem5 repository:
