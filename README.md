# RISC-V-MYTH-WORKSHOP

## Microprocessor for You in Thirty Hours

This repository contains my complete documentation, implementation work, experiments, simulation results, and learning outcomes from the **RISC-V MYTH Workshop** conducted by **VLSI System Design (VSD)** in collaboration with **Redwood EDA**.

The workshop provided hands-on exposure to the **RISC-V Instruction Set Architecture (ISA)**, processor architecture, software-hardware interaction, **TL-Verilog**, and the development of a RISC-V processor using the **Makerchip** platform.

---

## 📌 About the Workshop

The **MYTH (Microprocessor for You in Thirty Hours)** workshop is a practical introduction to processor design using the open RISC-V ISA.

The workshop follows a progression from understanding how software executes on a processor to designing the hardware required to execute RISC-V instructions.

The overall learning flow can be summarized as:

```text
RISC-V ISA
     │
     ▼
RISC-V Software Toolchain
     │
     ▼
C → Assembly → Machine Code
     │
     ▼
Instruction Encoding & ABI
     │
     ▼
TL-Verilog
     │
     ▼
Digital Logic & Processor Datapath
     │
     ▼
RISC-V Core
     │
     ▼
Pipelining
     │
     ▼
Simulation & Verification
```

---

# 🎯 Workshop Objectives

The main objectives of this workshop were to:

* Understand the fundamentals of the RISC-V ISA.
* Learn the RV32I instruction set.
* Understand how high-level C programs are translated into machine instructions.
* Explore the RISC-V GNU toolchain.
* Understand RISC-V registers and the ABI.
* Learn the fundamentals of TL-Verilog.
* Understand processor datapath design.
* Implement a RISC-V processor core.
* Introduce pipelining into the processor.
* Simulate and analyze processor behavior.
* Gain practical experience with open-source hardware design tools.

---

# 📚 Workshop Documentation

The workshop documentation is divided according to the individual workshop days.

|    Day    | Topic                                       | Documentation     |
| :-------: | ------------------------------------------- | ----------------- |
| **Day 1** | Introduction to RISC-V & Software Toolchain | [Day 1](./Day-1/) |
| **Day 2** | RISC-V ISA, ABI & Basic Architecture        | [Day 2](./Day-2/) |
| **Day 3** | TL-Verilog & Basic Processor Design         | [Day 3](./Day-3/) |
| **Day 4** | RISC-V Core Implementation                  | [Day 4](./Day-4/) |
| **Day 5** | Pipelining, Verification & Final Core       | [Day 5](./Day-5/) |

> The exact contents of each day are documented in the corresponding `README.md`.

---

# 🗂️ Repository Structure

```text
RISC-V-MYTH-Workshop/
│
├── README.md
│
├── Day-1/
│   ├── README.md
│   ├── images/
│   ├── code/
│   └── outputs/
│
├── Day-2/
│   ├── README.md
│   ├── images/
│   ├── code/
│   └── outputs/
│
├── Day-3/
│   ├── README.md
│   ├── images/
│   ├── code/
│   └── outputs/
│
├── Day-4/
│   ├── README.md
│   ├── images/
│   ├── code/
│   └── outputs/
│
├── Day-5/
│   ├── README.md
│   ├── images/
│   ├── code/
│   └── outputs/
│
└── LICENSE
```

---

# 🔧 Tools & Technologies

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

# 🧠 Major Concepts Covered

## 1. RISC-V Instruction Set Architecture

The workshop introduces the RISC-V ISA and its modular approach to processor design.

Topics include:

* RISC vs CISC
* RISC-V ISA
* RV32I
* General-purpose registers
* Instruction formats
* Immediate values
* Instruction encoding
* Arithmetic and logical instructions
* Load/store instructions
* Branch and jump instructions

---

## 2. Software-Hardware Interaction

One of the important aspects of the workshop is understanding how a high-level program eventually becomes instructions executed by the processor.

```text
C Program
    │
    ▼
Compiler
    │
    ▼
RISC-V Assembly
    │
    ▼
Machine Code
    │
    ▼
RISC-V Processor
```

The RISC-V toolchain is used to compile and inspect programs at different stages of this process.

---

## 3. RISC-V ABI

The Application Binary Interface defines conventions used between software and the processor.

The workshop covers:

* RISC-V register conventions
* Register names
* Function calls
* Return addresses
* Stack usage
* Argument and return-value registers

---

## 4. TL-Verilog

TL-Verilog is used to describe the processor design at a higher level of abstraction while explicitly expressing timing and pipeline stages.

The workshop introduces concepts including:

* Signals
* Combinational logic
* Sequential logic
* Pipelines
* Timing abstraction
* Pipeline stages
* Validity

---

## 5. Processor Architecture

The processor development work covers the major components required for instruction execution.

```text
             ┌─────────────────┐
             │ Program Counter │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Instruction     │
             │ Fetch           │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Instruction     │
             │ Decode          │
             └────────┬────────┘
                      │
              ┌───────┴────────┐
              │                │
              ▼                ▼
       ┌─────────────┐   ┌─────────────┐
       │ Register    │   │ Immediate   │
       │ File        │   │ Generator   │
       └──────┬──────┘   └──────┬──────┘
              │                 │
              └────────┬────────┘
                       ▼
                ┌─────────────┐
                │     ALU     │
                └──────┬──────┘
                       │
                       ▼
                   Result
```

---

# 🚀 Processor Development

The processor implementation progresses through multiple stages during the workshop.

### Stage 1 — Basic Logic

Fundamental digital logic and sequential circuits are explored.

### Stage 2 — Instruction Execution

The processor datapath required to execute RISC-V instructions is developed.

### Stage 3 — RV32I Core

The major components of the RISC-V processor are integrated.

### Stage 4 — Pipelining

The processor is organized into pipeline stages using TL-Verilog timing abstraction.

### Stage 5 — Verification

Simulation and waveform analysis are used to verify processor behavior.

---

# 🧪 Verification & Simulation

The processor is tested using RISC-V programs and simulation.

The general verification flow is:

```text
       C Program
           │
           ▼
    RISC-V Compiler
           │
           ▼
    Assembly / Binary
           │
      ┌────┴─────┐
      │          │
      ▼          ▼
    Spike      RISC-V
  Simulator      Core
      │          │
      │          ▼
      │       Simulation
      │          │
      └────┬─────┘
           ▼
     Result Analysis
```

Simulation screenshots, waveforms, generated code, and relevant outputs are documented under the respective workshop day.

---

# 📁 Documentation Method

Each workshop day contains its own documentation.

Every day's directory is organized into:

```text
Day-X/
│
├── README.md
├── images/
├── code/
└── outputs/
```

### `README.md`

Contains:

* Topics covered
* Concepts learned
* Tasks performed
* Commands used
* Implementation details
* Results
* Key observations
* Learning outcomes

### `images/`

Contains relevant:

* Screenshots
* Architecture diagrams
* Makerchip views
* Waveforms
* Simulation results

### `code/`

Contains source files and code developed during the corresponding day.

### `outputs/`

Contains generated outputs and results where applicable.

---

# 📊 Learning Progression

The workshop provides a progression from software understanding to hardware implementation:

```text
Understanding RISC-V
        ↓
Understanding Instructions
        ↓
Understanding Software Execution
        ↓
Understanding Machine Code
        ↓
Understanding Processor Datapath
        ↓
Learning TL-Verilog
        ↓
Building the RISC-V Core
        ↓
Adding Pipeline Stages
        ↓
Simulation & Verification
```

---

# 💡 Key Learning Outcomes

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

# 🔭 Future Work

The work developed during the workshop provides a foundation for further exploration of RISC-V processor design.

Possible extensions include:

* Expanding RV32I instruction support
* Implementing additional pipeline stages
* Hazard detection
* Data forwarding
* Branch handling
* Memory interfaces
* FPGA implementation
* RTL synthesis
* Physical design using open-source EDA tools
* RISC-V ISA extensions
* Custom instructions for hardware acceleration

---

# 📜 Workshop Certificate

This repository serves as the technical documentation and evidence of work completed during the RISC-V MYTH Workshop.

**Certificate:** To be added after successful workshop completion.

---

# 🙏 Acknowledgements

I would like to thank **VLSI System Design (VSD)** and **Redwood EDA** for organizing the RISC-V MYTH Workshop and providing hands-on exposure to RISC-V processor design and open-source hardware development.

I also acknowledge the RISC-V open-source community and the developers of the tools used throughout this workshop.

---

## 🔗 Useful Resources

* [RISC-V International](https://riscv.org/)
* [VLSI System Design](https://www.vlsisystemdesign.com/)
* [Makerchip](https://makerchip.com/)
* [RISC-V GNU Toolchain](https://github.com/riscv-collab/riscv-gnu-toolchain)
* [Spike RISC-V ISA Simulator](https://github.com/riscv-software-src/riscv-isa-sim)

---

## 👨‍💻 Author

**Abin Abraham**

Electronics & Computer Engineering
Saintgits College of Engineering

[GitHub](https://github.com/Abin-Abraham248) · [LinkedIn](https://linkedin.com/in/abin-abraham248)
