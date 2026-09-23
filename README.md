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

---

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
---

## Introduction to ABI
System programming involves designing and writing computer programs that allow the computer hardware to interface with the programmer and the user, leading to the effective execution of application software on the computer system. In order to achieve systems programming there needs to be an interface which communicates between software and hardware which is where the APPLICATION BINARY INTERFACE comes into play.

Application Binary Interface is an interface that allows application programmers to access hardware resources. RISC-V specification has 32 registers whose width is defined by XLEN which can be 32/64 for RV32/RV64 respectively.The data can be loaded from memory to registers or directly sent, Application programmer can access each of these 32 registers through its ABI name seen below

---

## Digital Logic with TL-Verilog and Makerchip
### MAKERCHIP
Makerchip is a free online environment by Redwood EDA for developing high-quality integrated circuits. The online platform can be used to code, compile, simulate and debug Verilog designs all in just one tool. Access and learn from here

### TL VERILOG
Transaction Level Verilog or TL-Verilog is an extension to existing Verilog HDL and a huge step forward in coding HDL languages. TL-Verilog introduces simpler syntaxes and adds powerful constructs which makes Logic Design fun and easy. (Also can say its a Higher Abstraction to Sys V). Generally, high-speed designs are less than half the size in TL-Verilog versus SystemVerilog without any loss in detail! More about it here

### DIGITAL DESIGN
Below are a set of images from Makerchip showcasing the TL-V code for Combinational and sequential logic and Simulation Output. Most of the basic circuits examples can be found in Makerchip Tutorials anexhaustive list to get anyone enough information to learn the platform and TL-Verilog.

---

## RISC-V Core Implementation
Basic processor of 3 stages fetch, decode and execute based on RISC-V ISA.

### Program Counter
The program counter (PC), commonly called the instruction pointer (IP) is a counter in a processor that indicates where a computer is in its program. PC jumps 4bytes at a time as each instruction is 32bits in RV32.

### Fetch
The instruction fetch unit (IFU) in a central processing unit (CPU) is responsible for organising program instructions to be fetched from memory, and executed, in an appropriate order. This makes the control logic of the core.

### Decode
The decoding stage allows the CPU to determine what instruction is to be performed so that the CPU can tell how many operands it needs to fetch in order to perform the instruction. The opcode fetched from the memory is decoded for the next steps and moved to the appropriate registers. Below image shows hoe decode is determining the TYPE OF RISC V instructions set (Various types of Instructions in RV32 are I, R, S, J, U)

### Execute
An arithmetic-logic unit (ALU) is the part of the CPU that carries out arithmetic and logic operations. Below image shows an ADDI (ADD Immediate) instruction computation.

---

## RISC-V Pipelined Core
Converting non-piepleined CPU to pipelined CPU using timing abstract feature of TL-Verilog. This allows easy retiming wihtout any risk of funcational bugs.

The Core was enhanced to be staged across multi-stages in a pipeline, Final output where the core is computing Sum of 9 numbers and the code for the same is available

---

## Workshop Documentation

The workshop documentation is divided according to the individual workshop days.

|    Day    | Topic                                       | Documentation     |
| :-------: | ------------------------------------------- | ----------------- |
| **Day 1** | Introduction to RISC-V & Software Toolchain | [Day 1](./DAY%201/) |
| **Day 2** | RISC-V ISA, ABI & Basic Architecture        | [Day 2](./DAY%202/) |
| **Day 3** | TL-Verilog & Basic Processor Design         | [Day 3](./DAY%203/) |
| **Day 4** | RISC-V Core Implementation                  | [Day 4](./DAY%204_5/) |
| **Day 5** | Pipelining, Verification & Final Core       | [Day 5](./DAY%204_5/) |

> The exact contents of each day are documented in the corresponding `README.md`.

---



## Conclusion
This project was done as a part of the RISC-V based MYTH (Microprocessor for You in Thirty Hours) workshop conducted by Kunal Ghosh and Steve Hoover. The current project implements almost the entire RV32I base instruction set. We capable of executing all RISC-V instructions in four cycles with easy pipelining using Transaction-Level Verilog. TL-Verilog not only reduces your code size significantly but allows us to freely declare signals without explicitly declaring them (just like Python does compare to C). In addition, we can generate Verilog/SystemVerilog code from TL-Verilog in Makerchip IDE which using Sandpiper complier. Future work involves modifying the current design to implement support for the remaining operations and also implementation of other standard extensions like M, F and D.

<!--
## Workshop Certificate

This repository serves as the technical documentation and evidence of work completed during the RISC-V MYTH Workshop.

**Certificate:** To be added after successful workshop completion.

---
-->
---

## Acknowledgements

I would like to thank **VLSI System Design (VSD)** and **Redwood EDA** for organizing the RISC-V MYTH Workshop and providing hands-on exposure to RISC-V processor design and open-source hardware development. Also thanking the mentors 

* [Kunal Ghosh](https://github.com/stevehoover/), Co-founder, [VSD Corp. Pvt. Ltd](https://www.redwoodeda.com/).
* [Steve Hoover](https://github.com/kunalg123/), Founder, [Redwood EDA](https://www.vlsisystemdesign.com/).
---



