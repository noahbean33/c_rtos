# Custom Real-Time Operating System (RTOS) Implementations

A collection of custom RTOS implementations built from first principles on ARM Cortex-M microcontrollers, demonstrating deep understanding of operating system internals, embedded systems programming, and low-level hardware interaction.

## Overview

This repository contains multiple complete RTOS implementations written in C and ARM assembly, showcasing advanced embedded systems concepts including kernel design, context switching, scheduling algorithms, and inter-process communication mechanisms. All implementations are built for bare-metal ARM Cortex-M processors without relying on existing RTOS frameworks.

## Technical Skills Demonstrated

- **Low-level Systems Programming**: Bare-metal C and ARM assembly
- **Operating System Design**: Kernel architecture, thread management, context switching
- **Real-Time Scheduling**: Multiple scheduling algorithm implementations
- **Embedded Hardware**: Direct register manipulation, interrupt handling, peripheral drivers
- **Synchronization Primitives**: Semaphores, mutexes, mailboxes, FIFO queues
- **ARM Architecture**: Cortex-M stack manipulation, exception handling, SysTick, PendSV

## Repository Structure

### Primary Implementations

This repository contains two complete RTOS implementations from different sources:

#### 1. `Build_your_own_RealTime_OS-main/` (Most Complete)
**Hardware Target**: STM32 Nucleo F429ZI  
**IDE Support**: STM32CubeIDE, Keil µVision

**Key Projects**:
- **Build_a_RTOS**: Complete round-robin scheduler with context switching
- **Cooperative_Scheduler**: Non-preemptive cooperative multitasking
- **Periodic_Scheduler_ver_1 & ver_2**: Time-triggered periodic task execution
- **Spinlock_Semaphore**: Thread synchronization with spinlock and cooperative semaphores
- **Priority_Scheduler**: Preemptive priority-based scheduling
- **Hardware Drivers**: LED, UART, GPIO, ADC, Timer peripheral drivers
- **Documentation**: Complete ARM reference manuals and datasheets

#### 2. `rtos_ground_up-master/`
**Hardware Target**: STM32F411 Discovery Board  
**Build System**: Makefiles

**Key Projects**:
- **asm_primer**: Assembly language primer demonstrating low-level ARM programming
- **kernal_internals**: Core kernel concepts and thread control blocks
- **systick_scheduler**: SysTick-based round-robin scheduler
- **semaphore/cooperative**: Cooperative thread yielding with semaphores
- **semaphore/spin_lock**: Spinlock-based synchronization
- **scv_services**: Supervisor call (SVC) handler implementation
- **periodic_scheduler**: Periodic task scheduling with hardware timers

## Core Components Implemented

### Schedulers
- **Round-Robin (RR)**: Time-sliced fair scheduling with configurable quantum
- **Cooperative**: Voluntary context switching via thread yield
- **Periodic**: Time-triggered scheduling with multiple implementation approaches
- **Priority-based**: Preemptive scheduling based on thread priority
- **Sporadic**: Event-driven sporadic task scheduling
- **Fixed/Rate Monotonic**: Fixed priority periodic scheduling

### Kernel Features
- **Thread Control Blocks (TCB)**: Complete thread state management
- **Context Switching**: Full register save/restore in assembly
- **Stack Management**: Individual thread stacks with overflow protection
- **SysTick Integration**: 1ms system tick for time-sliced scheduling
- **PendSV Handler**: Efficient context switching using PendSV exception

### Synchronization & IPC
- **Spinlock Semaphores**: Busy-wait synchronization primitives
- **Cooperative Semaphores**: Non-blocking thread coordination
- **Mailboxes**: Thread-to-thread message passing
- **FIFO Queues**: Buffered inter-thread communication
- **Thread Sleep**: Delay functionality with scheduler integration

### Hardware Abstraction
- **GPIO Drivers**: Digital I/O control
- **UART Driver**: Serial communication for debugging
- **LED Driver**: Visual feedback and testing
- **Timer/PWM**: Hardware timer configuration
- **ADC**: Analog-to-digital conversion
- **Timebase**: Millisecond timing utilities

## Technical Implementation Details

### ARM Cortex-M Features Used
- **Dual Stack Pointers (MSP/PSP)**: Separate kernel and thread stacks
- **Exception Handling**: SysTick, PendSV for context switching
- **NVIC Configuration**: Interrupt priority management
- **Thumb-2 Instruction Set**: Efficient 16/32-bit mixed code
- **xPSR Register**: Processor state management

### Context Switch Implementation
Context switching is implemented in pure assembly using:
- Register banking (R4-R11 manual save/restore)
- Hardware-assisted save/restore (R0-R3, R12, LR, PC, xPSR)
- Stack pointer manipulation
- Thread control block linked list traversal

### Memory Architecture
- **Static Memory Allocation**: Fixed-size thread stacks
- **Circular Linked Lists**: TCB management for efficient scheduling
- **Stack Overflow Detection**: Canary values and boundaries

## Development Environment

**Microcontrollers**:
- STM32F429ZITx (ARM Cortex-M4, 180MHz, 2MB Flash, 256KB RAM)
- STM32F411VETx (ARM Cortex-M4, 100MHz, 512KB Flash, 128KB RAM)

**Toolchains**:
- ARM GCC Compiler
- STM32CubeIDE
- Keil µVision 5 (MDK-ARM)
- GNU Make

**Debugging**:
- SWD/JTAG hardware debugging
- UART serial output
- Logic analyzer integration

## Code Quality & Design

- **Well-commented**: Extensive inline documentation explaining low-level operations
- **Modular Design**: Clear separation between kernel, drivers, and application code
- **Multiple Implementations**: Different approaches to same problems for comparison
- **Testing**: Dedicated test applications for each scheduler and feature
- **Production-Ready**: Includes error handling and boundary checks

## Learning Outcomes

This repository demonstrates proficiency in:
- Writing production-quality embedded C code
- ARM assembly language programming
- Understanding CPU architecture and execution modes
- Implementing complex data structures in constrained environments
- Real-time system design and analysis
- Hardware-software co-design
- Interrupt-driven programming
- Resource management in embedded systems

## Documentation

The `Build_your_own_RealTime_OS-main/Documentation/` folder contains comprehensive technical references including ARM Cortex-M4 reference manuals, STM32 datasheets, HAL documentation, and board schematics—totaling over 75MB of technical documentation used during development.