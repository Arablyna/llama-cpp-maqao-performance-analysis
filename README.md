# Llama.cpp MAQAO Performance Analysis

This repository contains a performance analysis report of **llama.cpp** during the **Prompt Processing** phase of Large Language Model inference.

The project was carried out as part of the **Architecture and Code Optimization for High-Performance Microprocessors** course. The goal was to analyze a real LLM inference workload on CPU using **MAQAO**, with a focus on profiling, scalability, compiler impact, and bottleneck identification.

## Overview

Large Language Model inference is computationally intensive and strongly depends on hardware characteristics such as CPU architecture, cache hierarchy, memory bandwidth, vectorization, threading, and compiler optimizations.

In this project, **llama.cpp** was selected as a real-world case study because it is an optimized C/C++ framework for local LLM inference. The analysis focuses on the **Prompt Processing** phase, where input tokens are processed before text generation.

The study uses **MAQAO ONEview** to profile the execution, analyze CPU behavior, evaluate scalability, and identify performance limitations.

## Report

The full report is available here:

[Read the full PDF report](./Rapport_projet_AOC_Meguellati_Arab.pdf)

## Tools and Technologies

- llama.cpp
- MAQAO ONEview
- GCC
- Clang / LLVM
- Intel ICX
- Linux
- C / C++
- CPU profiling
- Scalability analysis
- Compiler comparison

## Models Studied

The experiments were conducted on quantized LLaMA models in GGUF format, including:

- Meta-Llama-3.1-8B
- Meta-Llama-3.2-3B

## Experiments

The report covers several experimental configurations:

- Sequential execution with one CPU thread
- Multi-threaded execution
- Stability analysis across repeated runs
- Scalability analysis with different thread counts
- Compiler comparison between GCC, Clang, and Intel ICX
- Analysis of CPU activity, memory pressure, thread affinity, and parallel efficiency

## Key Observations

The experiments show that multi-threading improves execution time, but the speedup is not linear.

One experiment shows a runtime reduction from approximately **76.84 seconds** in sequential execution to **39.72 seconds** with 8 threads. This corresponds to a speedup of about **1.93×**, with limited parallel efficiency.

The analysis suggests that performance is affected by:

- memory pressure caused by large model weights
- limited scalability when increasing the number of threads
- thread affinity instability
- cache locality issues
- compiler optimization choices
- dominant execution time inside optimized `ggml` / `llama.cpp` computation kernels

## Skills Demonstrated

This project demonstrates practical experience in:

- HPC performance analysis
- LLM inference benchmarking
- CPU profiling with MAQAO
- Scalability evaluation
- Compiler comparison
- Bottleneck identification
- Technical reporting
- Analysis of compute-bound and memory-bound behavior

## Repository Structure

```text
.
├── README.md
└── Rapport_projet_AOC_Meguellati_Arab.pdf
