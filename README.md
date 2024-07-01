# Computer Architecture and Related Concepts

## Define the term computer architecture.
Computer architecture refers to the design and organization of a computer's components and systems, including the hardware, software, and firmware, to achieve desired performance and efficiency.

## Classification of Memory

### Primary Memory
- **RAM (Random Access Memory):** Volatile memory used for storing data and machine code currently in use.
- **ROM (Read-Only Memory):** Non-volatile memory used to store firmware.

### Secondary Memory
- **Hard Drives:** Magnetic storage devices used for long-term data storage.
- **Solid State Drives (SSD):** Faster, more reliable storage devices using flash memory.

### Cache Memory
- **L1 Cache:** Small, fast memory located inside the CPU.
- **L2 Cache:** Larger and slower than L1, but faster than main memory.
- **L3 Cache:** Even larger and slower, shared among multiple CPU cores.

### Virtual Memory
- **Paging:** Memory management scheme that eliminates the need for contiguous allocation of physical memory.
- **Segmentation:** Memory management technique that divides the program into segments.

## Control Sequencing for Executing the Instruction `Add r4, r5, r6`

1. **Fetch:** Load the instruction from memory into the instruction register.
2. **Decode:** Determine the operation (ADD) and identify the registers involved (r4, r5, r6).
3. **Read Operands:** Retrieve the values stored in r5 and r6.
4. **Execute:** Perform the addition operation on the values in r5 and r6.
5. **Write Back:** Store the result of the addition in register r4.

## Define RAM
RAM (Random Access Memory) is a type of volatile memory that stores data and machine code currently being used. It allows data items to be read or written in almost the same amount of time irrespective of the physical location of data inside the memory.

## What are EPROMs?
EPROM (Erasable Programmable Read-Only Memory) is a type of ROM that can be reprogrammed and erased by exposing it to UV light.

## What is SRAM and DRAM?

- **SRAM (Static RAM):** Faster, more expensive memory used for cache memory. It does not need to be periodically refreshed.
- **DRAM (Dynamic RAM):** Slower, less expensive memory used for main memory. It needs to be periodically refreshed to maintain the stored data.

## Define Memory Address Register (MAR)
The Memory Address Register (MAR) holds the address of the memory location that is to be read from or written to.

## List the types of data hazards

1. **Read After Write (RAW):** Occurs when a read operation follows a write operation on the same data.
2. **Write After Read (WAR):** Occurs when a write operation follows a read operation on the same data.
3. **Write After Write (WAW):** Occurs when a write operation follows another write operation on the same data.

## What is a bus? Draw the single bus structure.
A bus is a communication system that transfers data between components of a computer. 

![Single Bus Structure](https://upload.wikimedia.org/wikipedia/commons/thumb/0/02/Single_bus_structure.png/300px-Single_bus_structure.png)

## What is associative memory?
Associative memory, or content-addressable memory (CAM), is a type of memory that allows data to be accessed based on content rather than specific addresses.

## Describe the different steps involved in data transfers through DMA with a block diagram

1. **CPU initiates the DMA transfer:** The CPU sets up the DMA controller by providing the necessary parameters such as the source and destination addresses, and the amount of data to be transferred.
2. **DMA controller takes control of the bus:** The DMA controller takes control of the system bus and starts the data transfer process.
3. **Data is transferred directly between I/O device and memory:** The DMA controller transfers data directly between the I/O device and memory without involving the CPU.
4. **DMA controller informs CPU after transfer completion:** Once the data transfer is complete, the DMA controller sends an interrupt signal to the CPU to inform it that the transfer is complete.

![DMA Controller](https://media.geeksforgeeks.org/wp-content/uploads/20230509110159/DMA-Controller-660.webp)

## Pros and Cons of DMA

### Pros
- Frees the CPU from handling data transfers.
- Increases system throughput.
- Allows for high-speed data transfer.

### Cons
- Complexity in DMA controller design.
- Potential for bus contention.
- Requires careful handling of interrupts.

## Difference Between Hardwired Control and Microprogrammed Control

- **Hardwired Control:** Utilizes fast, fixed logic circuits, making it difficult to modify.
- **Microprogrammed Control:** Uses a control memory to store control signals, making it slower but easier to modify and implement complex instructions.

## Addressing Modes and Their Explanation with Diagrams

1. **Immediate Addressing Mode:**
   - Operand is part of the instruction.
   - Example: `ADD R1, #5` (Adds the value 5 to R1).

2. **Direct Addressing Mode:**
   - Address of the operand is given in the instruction.
   - Example: `ADD R1, 5000` (Adds the value at address 5000 to R1).

3. **Indirect Addressing Mode:**
   - Address of the address of the operand is given in the instruction.
   - Example: `ADD R1, (5000)` (Adds the value at the address stored in address 5000 to R1).

4. **Register Addressing Mode:**
   - Operand is in a register.
   - Example: `ADD R1, R2` (Adds the value in R2 to R1).

5. **Register Indirect Addressing Mode:**
   - Register contains the address of the operand.
   - Example: `ADD R1, (R2)` (Adds the value at the address stored in R2 to R1).

6. **Displacement Addressing Mode:**
   - Combines a base address with an offset.
   - Example: `ADD R1, 5000(R2)` (Adds the value at address 5000 + value in R2 to R1).

7. **Stack Addressing Mode:**
   - Operand is on the top of the stack.
   - Example: `POP R1` (Removes the top value from the stack and stores it in R1).

## Conversion Between Number Systems

### Convert 0.6875 to Binary
- 0.6875 in binary is `0.1011`.

### Convert 0.011010 to Decimal
- 0.011010 in decimal is `0.203125`.

## Difference Between Synchronous and Asynchronous Bus

- **Synchronous Bus:**
  - Operates with a clock signal.
  - Data transfer is synchronized with the clock.

- **Asynchronous Bus:**
  - No clock signal.
  - Data transfer is controlled by handshaking.

## Advantages of Multiple Bus Organization Over Single Bus Organization

- **Increased Parallelism:** Multiple buses allow for simultaneous data transfers.
- **Reduced Bottlenecks:** Data traffic is distributed across multiple buses, reducing congestion.
- **Higher Throughput:** Overall data transfer rate is improved.
- **Better Fault Tolerance:** System can continue to operate even if one bus fails.

## Flow Chart for Addition and Subtraction of Floating Point Numbers

1. **Align Exponents:** Adjust the exponents so they match.
2. **Add or Subtract Significands:** Perform the addition or subtraction on the significands.
3. **Normalize the Result:** Adjust the result to ensure it fits the floating-point format.
4. **Round if Necessary:** Round the result to the appropriate precision.
5. **Handle Special Cases:** Address issues such as overflow and underflow.

## Interrupts

### Definition
Signals that alter the sequence of execution in a computer.

### Handling
1. Save the current state of the CPU.
2. Execute the interrupt service routine (ISR).
3. Restore the previous state of the CPU and resume execution.

### Comparison Between Memory Mapped I/O and I/O Mapped I/O

- **Memory Mapped I/O:** Uses the same address space for I/O devices and memory, allowing instructions like `LOAD` and `STORE` to access devices.
- **I/O Mapped I/O:** Uses a separate address space for I/O operations, requiring special instructions like `IN` and `OUT` for data transfer.

## Difference Between RISC and CISC

- **RISC (Reduced Instruction Set Computing):**
  - Simple instructions that can be executed within a single clock cycle.
  - Emphasizes efficiency and speed.

- **CISC (Complex Instruction Set Computing):**
  - Complex instructions that may take multiple clock cycles to execute.
  - Emphasizes a rich set of instructions for more complex operations.
