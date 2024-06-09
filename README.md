# MIPS Processor Design

## Overview

This repository contains the implementation of a MIPS processor, both in non-pipelined and pipelined designs. The project includes two programs: a sorting algorithm and a factorial computation. The designs are implemented in Python and simulate the MIPS architecture with instruction fetch, decode, execute, memory access, and write-back stages.

### Non-Pipelined MIPS Processor

#### Description

The non-pipelined MIPS processor in this project reads machine code instructions, decodes them, executes them using an ALU, accesses data memory, and writes back to the register file. It handles substantial programs like sorting and factorial computation. The machine code instructions for programs like sorting and factorial computation are hardcoded in the codebase.


#### Implementation Details

- **Instruction Memory**: Contains machine code instructions.
- **Data Memory**: Stores data accessed by instructions.
- **Register File**: Maintains register values.
- **Pipeline Stages**:
  - **Instruction Fetch (IF)**
  - **Instruction Decode (ID)**
  - **Execute (EX)**
  - **Memory Access (MEM)**
  - **Write Back (WB)**

#### Functions

- `fetch()`: Reads instructions from instruction memory.
- `decode()`: Decodes instructions and prepares for execution.
- `execute()`: Performs ALU operations and control flow handling.
- `memory()`: Accesses data memory for load/store instructions.
- `write_back()`: Writes results back to the register file.
- `control_signal()`: Generates control signals based on the instruction.
- `twos_complement()`: Converts negative binary offset.
- `sign_extend()`: Extends 16-bit values to 32-bit.

### Pipelined MIPS Processor

The pipelined MIPS processor in this project enhances performance by fetching a new instruction every cycle, utilizing instruction-level parallelism. It includes forwarding and hazard detection units to handle data and control hazards.

#### Description

The pipelined processor improves performance by fetching a new instruction every cycle, implementing instruction-level parallelism. It includes forwarding and hazard detection units to handle data and control hazards.

#### Implementation Details

- **Pipeline Registers**: IF_ID, ID_EX, EX_MEM, MEM_WB.
- **Forwarding Unit**: Resolves data hazards by forwarding values.
- **Hazard Detection Unit**: Detects and handles hazards, inserts stalls, or flushes the pipeline when necessary.

#### Functions

- `fetch()`: Updates pipeline registers with fetched instructions.
- `decode()`: Decodes instructions using values from pipeline registers.
- `execute()`: Executes instructions, considering forwarding if necessary.
- `memory()`: Accesses data memory, handles memory hazards.
- `write_back()`: Writes results back to the register file.
- `forwarding_unit()`: Generates forwarding signals for data hazards.
- `hazard_detection_unit()`: Detects hazards and manages stalls or pipeline flushes.
- `control_hazard()`: Handles control hazards by flushing the pipeline.

