# RTOS-C-Rust-Comparison

## STM32 Nucleo Language License

A minimal Real-Time Operating System (RTOS) implemented in C and enhanced with Rust concurrency features for the STM32 Nucleo-F446RE, with a performance and usability comparison. 



## Project Overview

This repository contains a minimal RTOS designed for the STM32 Nucleo-F446RE microcontroller. The RTOS is first implemented in C with basic task scheduling and semaphore-based synchronization. A Rust component is then integrated, replacing the semaphore with a Mutex to manage a shared resource. The project compares the performance (context switch time, resource access latency) and ease of concurrency implementation between C and Rust, testing the hypothesis that Rust offers safer and potentially faster concurrency.



## Features

- **Task Management**: 2–3 static tasks (LED blinking, UART printing)
- **Scheduler**: Round-robin scheduling using the SysTick timer
- **Concurrency**: C semaphore vs. Rust Mutex for a shared UART buffer
- **Hardware**: STM32 Nucleo-F446RE (ARM Cortex-M4, 180 MHz, 512 KB Flash)



## Goals

- Build a functional RTOS in C  
- Enhance it with Rust concurrency primitives  
- Compare C and Rust in terms of performance and programmer experience  
- Explore Rust’s applicability in embedded RTOS development


## Repository Structure


## Getting Started

### Prerequisites

**Hardware**:
- STM32 Nucleo-F446RE board with ST-LINK debugger

**Software**:
- STM32CubeIDE for C development
- Rust Toolchain (nightly) for `no_std` support
- Rust crates: `cortex-m-rt`, `stm32f4xx-hal` (install via `cargo`)
- Tools: OpenOCD or ST-LINK Utility for flashing and debugging



### Installation


### Project Timeline
Weeks 1–2: Setup and learning (Udemy courses at 2x speed)

Weeks 3–5: C RTOS implementation and testing

Weeks 6–8: Rust concurrency integration

Weeks 9–11: Performance measurement, demo, and report

Total Effort: ~53–68 hours over 11 weeks




###License

###Acknowledgments
