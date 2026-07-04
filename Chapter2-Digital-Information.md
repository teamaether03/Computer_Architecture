# CHAPTER 2 - Digital Information

---

## 1. Digital Information

Digital Information is any information represented using discrete values, almost always binary (0 and 1), so computers can store, process, and transmit it reliably.

Digital computers represent everything using only two states:

```text
0 = OFF / Low Voltage / False

1 = ON / High Voltage / True
```

### How Information is Represented

| Real-world Data | Digital Representation |
| --------------- | ---------------------- |
| Text | ASCII / Unicode |
| Number | Binary |
| Image | Pixels (binary values for colors) |
| Audio | Samples (binary numbers) |
| Video | Sequence of digital images + audio |

### Example :

```text
letter : A

ASCII : 65

Binary : 01000001
```

**Example 8-bit format:**

```python
print(format(65, '08b'))
```

**Example Convert Character → Binary:**

```python
print(format(ord('A'), '08b'))
```

---

## Bits

A Bit (Binary Digit) is the smallest unit of data. It is the smallest storage unit in a computer. it is one binary digit (0 or 1).

```text
CPU register = stores bits

RAM = stores bits

SSD = stores bits
```

---

## Bytes

A Byte = 8 bits.

### Basic Units

| Unit | Size |
|------|------|
| Bit | 0 or 1 |
| Nibble | 4 bits |
| Byte | 8 bits |
| KB | 1024 Bytes |
| MB | 1024 KB |
| GB | 1024 MB |
| TB | 1024 GB |

```text
0 and 1 => 2
```

### Linux Experiment: Size-check

```bash
echo "Hello" > file.txt

ls -lh file.txt
```

### Why 6 bits

```text
H

e

l

l

o

\n
```

---

## Binary

Binary is the number system used by computers. It is the language used to represent numbers and data in computers. the base-2 number system that uses bits (0 and 1) to represent numbers and all digital information.

### Example:

```text
Decimal: 5

Binary: 101
```

---

## Number Systems

Computers use multiple number systems.

| System | Base | Digits |
|---------|------|---------|
| Binary | 2 | 0,1 |
| Decimal | 10 | 0–9 |
| Octal | 8 | 0–7 |
| Hexadecimal | 16 | 0–9,A–F |

---

## Boolean Logic

Boolean Logic → AND, OR, NOT, XOR, NAND, and NOR are the foundation of every CPU, memory chip, and digital circuit.

### AND

Both conditions must be true.

### OR

At least one is true.

### NOT

Flips the value.

### XOR

Exclusive OR

Used heavily in:

- Cryptography
- Error detection
- CPU arithmetic

### NAND

NOT(AND)

Important: NAND is called a universal gate because any digital circuit (AND, OR, NOT, XOR, CPU logic, memory controllers, etc.) can be built using only NAND gates.


### NOT

NOT(OR) [Also a universal gate]

---
