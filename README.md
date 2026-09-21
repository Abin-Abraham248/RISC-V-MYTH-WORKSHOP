# RISC-V-MYTH-WORKSHOP

## Microprocessor for You in Thirty Hours

This repository contains my complete documentation, implementation work, experiments, simulation results, and learning outcomes from the **RISC-V MYTH Workshop** conducted by **VLSI System Design (VSD)** in collaboration with **Redwood EDA**.
The workshop provided hands-on exposure to the **RISC-V Instruction Set Architecture (ISA)**, processor architecture, software-hardware interaction, **TL-Verilog**, and the development of a RISC-V processor using the **Makerchip** platform.

---

## Workshop Objectives

The main objectives of this workshop were to:

* Understand the fundamentals of the RISC-V ISA.
* Understand how high-level C programs are translated into machine instructions.
* Explore the RISC-V GNU toolchain.
* Understand RISC-V registers and the ABI.
* Learn the fundamentals of TL-Verilog.
* Understand processor datapath design.
* Implement a RISC-V processor core.
* Introduce pipelining into the processor.
* Simulate and analyze processor behavior.

---
## Introduction to RISC-V ISA

An Instruction Set Architecture (ISA) defines, describes, and specifies how a particular computer processor core works. The ISA describes the registers and describes each machine-level instruction. The ISA forms the interface between hardware and software. Hardware engineers design digital circuits to implement a given ISA specification. Software engineers write code (operating systems, compilers, etc.) based on a given ISA specification.A RISC-V ISA is defined as a base integer ISA, which must be present in any implementation, plus optional extensions to the base ISA. Each base integer instruction set is characterized by

* Width of the integer registers (XLEN)
* Corresponding size of the address space
* Number of integer registers (32 in RISC-V)
* More details on RISC-V ISA can be obtained here.

## About GNU Compiler Tool Chain
The GNU Toolchain is a popular set of programming tools commonly used in Linux systems. The toolchain contains GNU Make, GCC, GNU Binutils, GNU Bison, GNU m4, GNU Debugger, and the GNU build system. Each of these tools help programmers make and compile their code to produce a program or library.

Under the risc-v toolchain,

* To use the risc-v gcc compiler use the below command:
```
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o <object filename> <C filename>
```
* More generic command with different options:
```
riscv64-unknown-elf-gcc <compiler option -O1 ; Ofast> <ABI specifier -lp64; -lp32; -ilp32> <architecture specifier -RV64 ; RV32> -o <object filename> <C      filename>
```
* More details on compiler options can be obtained here

* To view assembly code use the below command,
```
riscv64-unknown-elf-objdump -d <object filename>
```
To use SPIKE simualtor to run risc-v obj file use the below command,
```
spike pk <object filename>
```
To use SPIKE as debugger
```
spike -d pk <object Filename> with degub command as until pc 0 <pc of your choice>
```


## Introduction to ABI
System programming involves designing and writing computer programs that allow the computer hardware to interface with the programmer and the user, leading to the effective execution of application software on the computer system. In order to achieve systems programming there needs to be an interface which communicates between software and hardware which is where the APPLICATION BINARY INTERFACE comes into play.

Application Binary Interface is an interface that allows application programmers to access hardware resources. RISC-V specification has 32 registers whose width is defined by XLEN which can be 32/64 for RV32/RV64 respectively.The data can be loaded from memory to registers or directly sent, Application programmer can access each of these 32 registers through its ABI name seen below

## Workshop Documentation

The workshop documentation is divided according to the individual workshop days.

|    Day    | Topic                                       | Documentation     |
| :-------: | ------------------------------------------- | ----------------- |
| **Day 1** | Introduction to RISC-V & Software Toolchain | [Day 1](./DAY%201/) |
| **Day 2** | RISC-V ISA, ABI & Basic Architecture        | [Day 2](./DAY%202/) |
| **Day 3** | TL-Verilog & Basic Processor Design         | [Day 3](./DAY%203/) |
| **Day 4** | RISC-V Core Implementation                  | [Day 4](./DAY%204/) |
| **Day 5** | Pipelining, Verification & Final Core       | [Day 5](./DAY%205/) |

> The exact contents of each day are documented in the corresponding `README.md`.

---



---

## Tools & Technologies

The workshop makes use of a combination of software-development and hardware-design tools.

### Hardware / ISA

* RISC-V
* RV32I
* Processor Architecture
* RTL Design

### Hardware Description

* TL-Verilog
* Verilog concepts
* Makerchip

### Software

* C
* RISC-V Assembly
* RISC-V GNU Toolchain
* GCC
* Spike RISC-V ISA Simulator

### Development & Documentation

* Linux
* Git
* GitHub
* Markdown

---



## Key Learning Outcomes

After completing the workshop, the major areas of practical learning include:

* RISC-V ISA fundamentals
* RV32I instruction formats
* RISC-V assembly programming
* C-to-assembly compilation
* Machine-code analysis
* RISC-V ABI
* Processor datapath architecture
* Register-file design
* ALU and control logic
* TL-Verilog
* Pipeline design
* Processor simulation
* Waveform analysis
* Open-source processor development

---

<!--
## Workshop Certificate

This repository serves as the technical documentation and evidence of work completed during the RISC-V MYTH Workshop.

**Certificate:** To be added after successful workshop completion.

---
-->
## Acknowledgements

I would like to thank **VLSI System Design (VSD)** and **Redwood EDA** for organizing the RISC-V MYTH Workshop and providing hands-on exposure to RISC-V processor design and open-source hardware development. Also thanking the mentors 

* [Kunal Ghosh](https://github.com/stevehoover/), Co-founder, [VSD Corp. Pvt. Ltd](https://www.redwoodeda.com/).
* [Steve Hoover](https://github.com/kunalg123/), Founder, [Redwood EDA](https://www.vlsisystemdesign.com/).
---



