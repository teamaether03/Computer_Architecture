# CHAPTER 4 : MEMORY ARCHITECTURE

## 1. Registers

Registers are the smallest and fastest memory inside the CPU.

**Purpose :** Store data and instructions currently being processed.

### Characteristics :

- Inside CPU
- Fastest memory
- Very small (bytes to KB)
- Volatile

### Examples :

Program Counter (PC), Instruction Register (IR), General Purpose registers (RAX, RBX, etc.)

### Real Example :

When adding 5 + 10, both numbers are first loaded into registers before the ALU performs the addition.

---

## 2. Cache Memory

Cache is a very fast memory between the CPU and RAM.

**Purpose :** Reduce the time required to access frequently used data.

### Characteristics :

- Faster than RAM
- Smaller than RAM
- Volatile
- Stores recently/frequently used data

### Levels :

- L1 Cache (Fastest, smallest)
- L2 Cache
- L3 Cache (Largest, slowest among caches)

### Real Example :

Opening Chrome again is faster because required data may already be in cache.

---

## 3. RAM (Random Access Memory)

RAM is the main memory used while programs are running.

**Purpose :** Temporarily store active programs and data.

### Characteristics :

- Volatile
- Faster than SSD/HDD
- Larger than cache
- Can be read and written

### Real Example :

VS Code, Chrome, and games run from RAM.

---

## 4. ROM (Read Only Memory)

ROM is permanent memory that stores firmware.

**Purpose :** Store boot instructions permanently.

### Characteristics :

- Non-volatile
- Data remains after power off
- Mostly read-only

### Real Example :

BIOS/UEFI firmware is stored in ROM.

---

## 5. SSD (Solid State Drive)

SSD is a permanent storage device using flash memory.

**Purpose :** Store operating systems, files, and applications.

### Characteristics :

- Non-volatile
- Very fast
- No moving parts
- More reliable than HDD

### Real Example :

Windows boots much faster from an SSD.

---

## 6. HDD (Hard Disk Drive)

HDD is a storage device that uses spinning magnetic disks.

**Purpose :** Long-term storage of files.

### Characteristics :

- Non-volatile
- Slower than SSD
- Mechanical parts
- Cheaper per GB

### Real Example :

Older laptops commonly use HDDs.

---

# Memory Hierarchy

Memory hierarchy arranges memory from fastest to slowest and smallest to largest.

**Registers**

↓  

**L1 Cache**

↓  

**L2 Cache**

↓  

**L3 Cache**

↓  

**RAM**

↓  

**SSD**

↓  

**HDD**

### Speed Order :

Registers > Cache > RAM > SSD > HDD

### Size Order :

Registers < Cache < RAM < SSD < HDD

### Cost per GB :

Registers > Cache > RAM > SSD > HDD

### Why Memory Hierarchy?

No single memory can be:

- Fast
- Large
- Cheap

The hierarchy balances speed, capacity, and cost.

---

# Few Questions :

- **Why do CPUs use cache?**
- **Why is RAM called volatile?**
- **What is stored in ROM?**
- **Why is cache smaller than RAM?**

---
