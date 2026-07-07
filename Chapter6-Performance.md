# Chapter 6: Performance

## 1. Clock Speed

Clock Speed is the number of CPU cycles executed per second.

**Unit:** Hertz (Hz), GHz

**Example:** 3.5 GHz = 3.5 billion cycles/second.

**Note:** Higher clock speed does not always mean higher performance because IPC (Instructions Per Cycle) also matters.

**Experiment:**

```bash
cat /proc/cpuinfo | grep "MHz"
```

---

## 2. Cores

A core is an independent processing unit inside a CPU that can execute its own instructions.

**Example:**

8-core CPU = Can execute multiple tasks simultaneously.

**Note:** More cores improve multitasking and parallel workloads, not every single-threaded application.

**Experiment:**

```bash
lscpu
```

or

```bash
nproc
```

---

## 3. Threads

A thread is the smallest unit of execution handled by the CPU.

**Example:**

An 8-core CPU with Hyper-Threading may provide 16 threads.

**Note:** Threads improve CPU utilization by keeping execution units busy.

**Experiment:**

```bash
lscpu
```

Look for:

- CPU(s)
- Thread(s) per core
- Core(s) per socket

---

## 4. Cache

Cache is a small, ultra-fast memory inside the CPU that stores frequently accessed data.

### Levels

- L1 Cache (Fastest, Smallest)
- L2 Cache
- L3 Cache (Largest, Shared)

**Note:** Cache reduces RAM access time and improves CPU performance.

**Experiment:**

```bash
lscpu
```

---

## 5. Latency

Latency is the time taken to complete a single operation or receive a response.

**Unit:** Nanoseconds (ns), milliseconds (ms)

**Examples:**

- RAM latency
- Disk latency
- Network latency
- Important Point

**Lower latency = Faster response**

**Experiment:**

- **Memory Benchmark:**

```bash
sysbench memory run
```

- **Network Latency:**

```bash
ping google.com
```

---

## 6. Throughput

Throughput is the amount of work completed per unit of time.

**Examples:**

- Requests/second
- MB/s
- Transactions/second

**NOTE:** Higher throughput means more work is completed over time.

**Experiment:**

- **Disk Throughput:**

```bash
dd if=/dev/zero of=testfile bs=1G count=1 oflag=direct
```

- **Read Speed:**

```bash
dd if=testfile of=/dev/null bs=1G
```

---

## 7. Bottlenecks

A bottleneck is the component that limits the overall system performance.

**Examples:**

- Slow CPU
- Slow RAM
- Slow SSD
- Weak GPU
- Network bandwidth

**Important Point:**

Overall performance is limited by the slowest critical component.

**Experiment:**

- **Monitor CPU:**

```bash
top
```

- **Monitor Disk:**

```bash
iostat
```

- **Monitor Memory:**

```bash
free -h
```

- **Monitor All:**

```bash
vmstat 1
```

---

# Build-up Questions (One-Line Answers)

### 1. Does higher GHz always mean a faster CPU?

### 2. Why do modern CPUs have multiple cores?

### 3. What is the difference between a core and a thread?

### 4. Why is cache much faster than RAM?

### 5. What is latency?

### 6. What is throughput?

### 7. Which is better: low latency or high throughput?

### 8. What is a system bottleneck?

### 9. How can you check CPU information in Linux?

### 10. Which command shows CPU and memory usage in real time?
