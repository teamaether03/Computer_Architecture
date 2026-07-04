# Chapter 1 - What is Computer ?

---

## 1: What is a computer ?

A computer is a programmable electronic system that accepts input, processes data according to instructions, stores information, and produces output.

### Breaking it down

- Input → Keyboard, mouse, sensors, network packets
- Process → CPU executes instructions
- Store → RAM (temporary) and SSD/HDD (permanent)
- Output → Monitor, speakers, files, network responses

### More Technical Definition

A computer is a machine that executes instructions by manipulating binary data using hardware components coordinated by the operating system.

---

## 2: Hardware vs Software

### Hardware

Hardware is the physical, tangible components of a computer that you can touch.

Hardware performs the actual computation and stores data.

Example: CPU, RAM, SSD/HHD, Motherboard, etc.

### Software

Software is the set of instructions (programs) that tells the hardware what to do.

Software controls and utilizes hardware to perform tasks.

Example: Operating System (Linux, Windows), Chrome, VS Code, etc.

### How they work together

```text
User
  │
  ▼
Software (Chrome, Linux, Python)
  │
  ▼
Hardware (CPU, RAM, SSD, GPU)
  │
  ▼
Output
```

---

## 3: Input → Process → Output (IPO)

The Input–Process–Output (IPO) model explains how every computer works.

### Input:

Input is the data or instructions provided to the computer.

Examples: Keyboard typing, Mouse click, etc.

**Question answered:** What information does the computer receive?

### Process:

Processing is the execution of instructions on the input data, primarily by the CPU.

During processing, the computer may:

- Perform calculations
- Move data
- Read/write memory

**Question answered:** What does the computer do with the data?

### Output:

Output is the result produced after processing.

Examples: Text on a monitor, Sound from speakers, Network response, etc.

**Question answered:** What result does the user or another system receive?

> **NOTE :** Storage often works alongside IPO:

```text
Input → Process ↔ Storage → Output
```

RAM stores temporary data during processing.

SSD/HDD stores programs and files permanently.

---

## 4: Data vs Information

### Data

Data is raw, unprocessed facts or values that have little or no meaning by themselves.

Examples: 85, Mohit, etc.

### Information

Information is processed, organized, and meaningful data that can be used for understanding or decision-making.

Example: Mohit scored 85 marks in Computer Architecture.

### Key Difference :

| Data | Information |
|------|-------------|
| Raw facts | Processed facts |
| Input to processing | Output of processing |
| Cannot directly support decisions | Helps in making decisions |

> **NOTE :** CPU is responsible for processing the data.

---

# What is Abstraction ?

**Abstraction** is the process of hiding lower-level complexity and exposing only what is necessary to the layer above.

Abstraction allows engineers to build complex systems by focusing only on the current layer.

## Layers of Abstraction in a Computer:

```text
+----------------------------------+
| User                             |
+----------------------------------+
| Applications                     |
| (Chrome, VS Code, Games)         |
+----------------------------------+
| Operating System                 |
| (Linux, Windows)                 |
+----------------------------------+
| System Software                  |
| (Compiler, Linker, Loader)       |
+----------------------------------+
| Instruction Set Architecture     |
| (x86, ARM, RISC-V)               |
+----------------------------------+
| Microarchitecture                |
| (Pipeline, Cache, ALU, Registers)|
+----------------------------------+
| Digital Logic                    |
| (Logic Gates, Flip-Flops, MUX)   |
+----------------------------------+
| Transistors                      |
+----------------------------------+
| Electrons & Physics              |
+----------------------------------+
```

## Understanding Each Layer

### 1. User

Uses the computer without knowing how it works.

Example: Opening Chrome.

### 2. Applications

Programs that solve user problems.

Examples: Chrome, VS Code, Photoshop, etc.

### 3. Operating System

Manages hardware and provides services to applications.

Examples: Linux, Windows, macOS

### 4. System Software

Converts human-written code into machine code.

Examples: Compiler, Linker, Loader

### 5. Instruction Set Architecture (ISA)

Defines what instructions the CPU understands.

Examples: x86, ARM, RISC-V

### 6. Microarchitecture

Defines how the CPU actually executes those instructions.

Examples: ALU, Registers, Cache, Pipeline, Control Unit

### 7. Digital Logic

Builds CPU components using electronic circuits.

Examples: AND gate, OR gate, NOT gate, Multiplexers, Flip-Flops

### 8. Transistors

Tiny electronic switches that implement logic gates.

Modern CPUs contain billions of transistors.

### 9. Physics

Electric current, voltage, and semiconductor physics make transistors work.

## Real Example

When you press A on the keyboard:

```text
User
  ↓
Application receives key
  ↓
Operating System handles keyboard event
  ↓
CPU executes machine instructions (ISA)
  ↓
Registers and ALU process data
  ↓
Logic gates switch
  ↓
Transistors change state
  ↓
Electrical signals flow
```

## Key Idea

Each layer:

- **Uses** the layer below.
- **Hides** the complexity of the layer below.
- **Provides** simpler services to the layer above.

This is what makes modern computers programmable and scalable.

## One line Definition

Layers of abstraction organize a computer into multiple levels, where each layer hides the complexity of the layer below and provides simpler services to the layer above.

---

