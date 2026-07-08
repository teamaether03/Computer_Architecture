# Chapter 7 – System Workflow

---

# 1. Boot Process

The sequence of steps that starts a computer from power-on until the operating system is ready.

## Workflow

1. Power Button Pressed
2. Power Supply starts
3. CPU resets and executes BIOS/UEFI firmware
   - BIOS/UEFI performs POST (Power-On Self Test)
   - Hardware detection (RAM, CPU, SSD, Keyboard, etc.)
   - Bootloader is loaded (GRUB/Windows Boot Manager)
   - Bootloader loads the Operating System Kernel
   - Kernel initializes drivers and hardware
   - init/systemd starts services
   - Login Screen/Desktop appears

## Components

- CPU
- BIOS/UEFI
- CMOS
- Bootloader
- Kernel
- Drivers
- init/systemd

## Experiment

```bash
# Check boot logs
dmesg

# View current boot information
systemd-analyze

# Measure boot time
systemd-analyze time

# View boot process details
systemd-analyze blame
```

---

# 2. Running a Program

The process of loading an executable into memory and executing it using the CPU.

## Workflow

1. User launches program
2. OS finds executable file
3. Loader loads program into RAM
4. Virtual Memory is created
5. Shared libraries are loaded
6. CPU starts execution from main()
7. Scheduler gives CPU time
8. Program executes
9. Program exits
10. Memory is released

## Components

- Executable File
- Loader
- RAM
- CPU
- Scheduler
- Process
- Virtual Memory

## Experiment

```bash
# Compile
gcc hello.c -o hello

# Run
./hello

# Watch process
ps

# Real-time monitoring
top

# Show memory map
pmap <PID>
```

---

# 3. Opening a File

The process of accessing data stored on a storage device.

## Workflow

1. User requests file
2. File System searches metadata
3. OS checks permissions
4. File located on SSD/HDD
5. Required blocks loaded into RAM
6. Program reads file
7. Data displayed

## Components

- File System
- Inode
- Storage Device
- RAM
- Kernel
- Application

## Experiment

```bash
# Read file
cat file.txt

# Show file metadata
stat file.txt

# Watch system calls
strace cat file.txt
```

---

# 4. Keyboard Input

The process of converting key presses into data that applications can use.

## Workflow

1. Key pressed
2. Keyboard Controller detects key
3. Scan Code generated
4. Interrupt sent to CPU
5. Keyboard Driver processes code
6. OS converts scan code to character
7. Application receives input

## Components

- Keyboard
- Keyboard Controller
- Interrupt Controller
- CPU
- Driver
- Application

## Experiment

```bash
# Display keyboard events
sudo evtest

# OR
showkey

# (TTY only)
```

---

# 5. Mouse Input

The process of converting mouse movement and clicks into cursor actions.

## Workflow

1. Mouse moves
2. Sensor detects movement
3. Mouse sends movement packets
4. Interrupt generated
5. Driver interprets movement
6. OS updates cursor
7. Application receives event

## Components

- Mouse Sensor
- USB Controller
- Interrupt Controller
- Driver
- Window System

## Experiment

```bash
# Display mouse events
sudo evtest

# OR
xinput test <device-id>
```

---

# 6. Compilation Overview

The process of converting source code into machine code.

## Workflow

```text
Source Code
      ↓
Preprocessor
      ↓
Compiler
      ↓
Assembler
      ↓
Object File
      ↓
Linker
      ↓
Executable
```

## Stages

1. Preprocessing (.c → expanded code)
2. Compilation (C → Assembly)
3. Assembly (Assembly → Object File)
4. Linking (Object Files → Executable)

## Components

- Preprocessor
- Compiler
- Assembler
- Linker

## Experiment

```bash
# Preprocessing
gcc -E hello.c

# Compile to Assembly
gcc -S hello.c

# Compile to Object File
gcc -c hello.c

# Create Executable
gcc hello.c -o hello

# View Assembly
objdump -d hello
```

---

# 7. How Everything Works Together

## Complete Workflow

```text
Power Button
      ↓
BIOS / UEFI
      ↓
POST
      ↓
Bootloader
      ↓
Kernel
      ↓
Drivers Loaded
      ↓
Desktop/Login
      ↓
User Opens Program
      ↓
Executable Loaded into RAM
      ↓
CPU Executes Instructions
      ↓
Program Opens File
      ↓
Kernel Reads SSD/HDD
      ↓
File Loaded into RAM
      ↓
User Types Keyboard Input
      ↓
Interrupt Generated
      ↓
Driver Processes Input
      ↓
Application Receives Data
      ↓
User Clicks Mouse
      ↓
Interrupt Generated
      ↓
Application Responds
      ↓
Program Ends
      ↓
Memory Released
```

---
