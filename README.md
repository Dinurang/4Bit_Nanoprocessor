#  Nano Processor Design  


##  Overview  
This project implements a **4-bit Nano Processor** capable of executing a basic instruction set using a modular digital design approach. The processor was developed and tested on the **Basys 3 FPGA board** using VHDL.  
An **enhanced version** was later built, expanding the instruction set and adding more functional modules.

---

## Core Components (Basic Nano Processor)

### 1. Program ROM
Stores up to 8 hardcoded instructions (12-bit width). Delivers instructions based on the Program Counter value.

### 2. Instruction Decoder
Interprets the opcode and generates control signals such as:
- Register enables  
- ALU control signals  
- Jump signals  
- Immediate values

### 3. Program Counter (PC)
A 3-bit counter incremented every cycle, with support for jump instructions.

### 4. Register Bank
Contains eight 4-bit registers (`R0 – R7`).  
Supports write-enable selection through a 3-to-8 decoder.

### 5. Multiplexers
- 8-way 4-bit MUXes route selected registers into ALU inputs.  
- 2-way MUXes decide between arithmetic result or immediate value for register writes.

### 6. 4-bit Add/Sub Unit (ASU)
Handles:
- Addition  
- Subtraction using 2’s complement  
Produces Zero & Overflow flags.

### 7. 3-bit Adder
Increments the Program Counter.

### 8. Slow Clock Module
Generates a lower-frequency clock for stable FPGA operation.

### 9. Seven-Segment Display Decoder
Displays the content of register `R7`.

---

##  Execution Flow

1. Instruction Fetch  
2. Instruction Decode  
3. Operand Fetch  
4. Execute  
5. Write Back  
6. PC Update  

---

##  Basic Instruction Set

| Opcode | Mnemonic | Description |
|--------|----------|-------------|
| 00 | ADD | Add two registers |
| 01 | NEG | Subtract values |
| 10 | MOVI | Move immediate 4-bit value |
| 11 | JZR | Jump to address if register = 0 |

---

##  Improved Nano Processor (Enhanced Version)

### Added Components
- 4-bit Multiplier  
- Bit Comparator  
- AND, OR, XOR, NOT Units  
- Left & Right Shifters  
- Operation Selector  
- Improved Register Bank  
- Expanded Program ROM  

---

##  Conclusion
The nano processor successfully demonstrates modular CPU design.  
The improved version significantly enhances capability with arithmetic, logic, and shift operations, forming a strong foundation for future extensions.


## Please refer to the Report attached herewith to Learn More.