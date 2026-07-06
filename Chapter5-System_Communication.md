# Chapter 5 : System Communication

## 1. Motherboard

The motherboard is the main circuit board that connects and allows communication between all computer components.

**Purpose :**

- Connect CPU, RAM, Storage, GPU, Network Card, USB, etc.
- Provides power and communication paths.

### Main Components :

- CPU Socket
- RAM Slots
- PCIe Slots
- Chipset
- BIOS/UEFI Chip
- Storage Connectors (SATA/M.2)
- Power Connectors

### Real Flow :

```text
CPU
 │
Motherboard
 ├── RAM
 ├── SSD
 ├── GPU
 ├── USB
 └── Network Card
```

**Q: Why can't components communicate without a motherboard?**

Because the motherboard provides the physical connections and communication pathways.

---

## 2. Buses

A bus is a communication channel that transfers data between computer components.

### Types :

#### **Data Bus**

Transfers actual data.

**Example:** CPU → RAM

#### **Address Bus**

Carries memory addresses.

**Example :** CPU → Address 0x1000

#### **Control Bus**

Carries control signals.

**Example:** Read, Write, Interrupt, Clock

### Scenario Example : CPU wants data

- Address Bus → Memory Location
- Control Bus → Read
- Data Bus ← Data Returned

**Q: Difference between Data Bus and Address Bus?**

Data Bus transfers data; Address Bus specifies where the data is located.

---

## 3. Chipset (Overview)

The chipset manages communication between the CPU and other hardware.

Think of it as a traffic manager inside the motherboard.

### Responsibilities :

- USB communication
- SATA/NVMe storage
- PCIe devices
- Audio
- Networking

**NOTE :** Modern CPUs handle RAM directly, while the chipset manages slower peripherals.

```text
CPU
 │
Chipset
 ├── USB
 ├── SSD
 ├── Audio
 └── Ethernet
```

**Q: Why is a chipset needed?**

It manages communication between the CPU and peripheral devices.

### Few terms :

- **Serial Communication Interface:** A communication interface that transfers one bit of data at a time over a single communication channel.
- **Expansion Devices:** Hardware components added to a computer to provide new features or improve existing capabilities (e.g., GPU, Wi-Fi card, NVMe SSD, sound card).

---

## 4. PCIe (Peripheral Component Interconnect Express)

PCIe is a high-speed serial communication interface used to connect expansion devices.

### Used For :

- Graphics Card
- NVMe SSD
- Wi-Fi Card
- Capture Card
- AI Accelerator

### PCIe Lanes :

- x1
- x4
- x8
- x16

More lanes = More bandwidth.

### Example:

**GPU :** PCIe x16

**NVMe SSD :** PCIe x4

### Real Flow :

```text
CPU
 │
PCIe
 │
GPU
```

**Q: Why does a GPU use PCIe x16?**

Because GPUs require very high bandwidth.

---

## 5. Interrupts

An interrupt is a signal that tells the CPU to stop its current work and immediately handle an important event.

### Why Needed

**Without interrupts:**

```text
CPU keeps checking keyboard

Any key?

Any key?

Any key?

Waste of CPU time.
```

**With interrupts:**

```text
Keyboard pressed
        ↓
Interrupt sent
        ↓
CPU responds immediately
```

### Examples :

- Keyboard input
- Mouse movement
- Timer
- Disk completed
- Network packet received

### Flow :

```text
Device
   ↓
Interrupt
   ↓
CPU
   ↓
Interrupt Handler
   ↓
Resume Previous Task
```

**Q: Why are interrupts better than polling?**

Interrupts notify the CPU only when needed, while polling wastes CPU time by constantly checking devices.

---

## 6. Device Controllers

A device controller is hardware that manages communication between the CPU and a specific device.

### Examples :

- USB Controller
- Disk Controller
- Network Controller
- Keyboard Controller
- Display Controller

### Working :

```text
CPU
 ↓
Device Controller
 ↓
Actual Device
```

### Example :

```text
CPU
 ↓
USB Controller
 ↓
Pendrive
```

**NOTE :** The CPU communicates with the controller, not directly with the device.

### Linux Experiment :

- List USB devices : `lsusb`
- List storage devices : `lsblk`
- View hardware information : `lshw`

**Q: Why are device controllers required?**

They translate CPU commands into device-specific operations and manage communication with hardware.

---

## Summary Table

| **Topic** | **One-Line Definition** |
|-----------|--------------------------|
| Motherboard | Main circuit board that connects all hardware components. |
| Bus | Communication pathway for transferring data, addresses, and control signals. |
| Chipset | Manages communication between the CPU and peripheral devices. |
| PCIe | High-speed interface for connecting expansion devices like GPUs and NVMe SSDs. |
| Interrupt | Signal that tells the CPU to immediately handle an event. |
| Device Controller | Hardware that controls communication between the CPU and a specific device. |


---
