# Chapter 3: CPU Architecture

## 1. CPU (Central Processing Unit)

The CPU is the brain of the computer. It executes instructions, processes data, and controls the entire system.

### Purpose

- Executes programs
- Performs calculations
- Controls hardware
- Coordinates data movement

### Main components of CPU

- ALU (Arithmetic Logic Unit)
- Control Unit
- Registers

### IPO working

**Memory -> CPU -> Output Devices**

---

## 2. ALU (Arithmetic Logic Unit)

The ALU performs all mathematical and logical operations

### Types of operations ALU Performs

- Arithmetic (ex. Addition, Subtraction, etc.)
- Logical (ex. AND, OR, XOR, etc.)
- Comparison (ex. >, <, !=, <=, etc.)
- Bit Operation (ex. Left shift, Right shift, Rotate, etc.)

**Example:**

```text
00001010 << 1   ->   00010100
```

---

## 3. Control Unit (CU)

The Control Unit manages and coordinates every operation inside the CPU.

It does not calculate, It controls.

Think of it as the manager of a factory.

### Responsibilities

- Fetch instruction
- Decode instruction
- Tell ALU what to do
- Tell memory when to read/write
- Control data flow

### Example

- **Instruction ->** ADD A, B
- **Control Unit does:**

```text
Read instruction

↓

Understand "ADD"

↓

Load A

↓

Load B

↓

Tell ALU:

Add them

↓

Store result
```

---

## 4. Registers

Registers are the smallest and fastest memory inside the CPU.

They temporarily hold data while instructions execute.

### Why Registers?

Accessing RAM is slow. Registers are extremely fast.

CPU always tries to work using registers.

### Common Registers

- **Program Counter (PC)**

  Stores address of next instruction.

- **Instruction Register (IR)**

  Stores current instruction.

- **Accumulator (ACC)**

  Stores intermediate arithmetic results.

- **Memory Address Register (MAR)**

  Stores memory address to access.

  **Example:** MAR = 500 **means** read memory location 500

- **Memory Data Register (MDR)**

  Stores data being transferred.

- **Stack Pointer (SP)**

  Points to the top of the stack.

  **Used in**

  - Function calls
  - Local variables
  - Recursion

- **Flag Register**

  Stores result flags.

  **Example: Types of Flags :-**

  - Zero Flag
  - Carry Flag
  - Overflow Flag
  - Negative Flag
  - etc.

  **Example:** After 5 - 5

  Zero Flag Becomes **1.**

---

## 5. Clock

The clock synchronizes every operation inside the CPU. It produces regular electrical pulses.

Every CPU operation happens on these pulses.

**Example:** At every tick, it **Fetch, Decode, Execute, Access Memory,** etc.

### Clock Speed

Measured in HZ, KHz, MHz, GHz.

**Example:** 3 GHZ means 3 billion clock cycles er second.

### Notes

Higher clock speed does not always mean faster CPU.

Performance also depends on:

- IPC (Instructions Per Cycle)
- Cache
- Pipeline
- Core count
- Branch prediction
- Memory latency

---

## 6. Fetch–Decode–Execute Cycle

This is the CPU's continuous working loop.

**Fetch -> Decode -> Execute -> Repeat**

### Step 1: Fetch

CPU fetches instruction from RAM.

Uses: Program Counter, MAR, MDR.

### Step 2: Decode

Control Unit understands instruction.

Example: ADD, MOV, LOAD, STORE, etc.

### Step 3: Execute

ALU or another execution unit performs the operation.

**Example:**

```text
ADD

↓

10 + 5

↓

15
```

### Step 4: Store Result

Result goes to

- Register
- Cache
- RAM

---

# Practical Experiment (LINUX)

- Watch CPU information:

```bash
lscpu
```

- View CPU details:

```bash
cat /proc/cpuinfo
```

- Watch CPU usage live:

```bash
top
```

or

```bash
htop
```

- Observe Registers During Execution (Linux + GDB)

Compile:

```bash
gcc test.c -g -o test
```

Debug:

```bash
gdb ./test
```

Useful GDB commands:

```gdb
break main
run
layout regs
si          # Execute one instruction
info registers
x/i $pc     # Show current instruction
```

---

# One-Line Revision

- **CPU:** Executes instructions and controls the computer.
- **ALU:** Performs arithmetic, logical, comparison, and bitwise operations.
- **Control Unit:** Fetches, decodes, and coordinates instruction execution.
- **Registers:** Ultra-fast CPU storage for instructions, addresses, data, and results.
- **Clock:** Synchronizes CPU operations using clock cycles.
- **Fetch–Decode–Execute:** The fundamental instruction execution cycle repeated billions of times per second.

---
