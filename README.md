# Virtual Memory Simulation

## Overview

This project is developed as part of the **Computer Architecture** course. It serves as a simulation to understand the concept of **Virtual Memory**, **Page Tables**, and **Translation Lookaside Buffers (TLB)**. The program demonstrates how virtual memory addresses are translated into physical memory addresses using **TLB lookup**, **Page Table** mapping, and **Physical Memory management**.

## Features

- **Translation Lookaside Buffer (TLB):** Implements a small, fast memory that holds the mapping of recently used virtual pages to physical pages.
- **Page Table Simulation:** Simulates the structure of a page table, storing valid/invalid bits, dirty bits, and physical page numbers.
- **Physical Memory Simulation:** Stores data associated with virtual pages and supports read/write operations.
- **Random Address Generation:** Allows simulation of memory access patterns.
- **Hit & Miss Tracking:** Keeps track of TLB hits/misses and page table hits/misses.
- **Table Display:** Shows the current state of the **TLB**, **Page Table**, and **Physical Memory**.

## How It Works

1. The program starts by prompting the user for **physical page size, offset bits, virtual memory size, and TLB entries**.
2. The main menu provides various functionalities:
   - Input Data
   - Load Random Instructions
   - Read Data from Memory
   - Clear All Instructions
   - Show Memory Tables
   - Generate and Load Random Data
   - Exit the Program
3. When a virtual memory address is accessed:
   - It first checks the **TLB** for a hit.
   - If a **TLB miss** occurs, it checks the **Page Table**.
   - If a **Page Table miss** occurs, it loads the page into memory and updates the **Page Table** and **TLB**.
   - If the page is already in **physical memory**, it checks whether it needs to be updated or read.

## Code Structure

- **Data Structures:**
  - `TLBEntry`: Stores virtual page to physical page mappings.
  - `PageTableEntry`: Holds page table information including valid/dirty bits.
  - `PhysicalMemory`: Represents memory storage with mapped virtual pages.
- **Utility Functions:**
  - `binaryToDecimal()`, `decimalToHexadecimal()`, `hexadecimalToBinary()`, etc.
- **Simulation Functions:**
  - `TLBCheck()`, `physicalMemoryCheck()`, `showTLBTable()`, `showPageTable()`, `showPhysicalMemory()`.
- **Main Loop:**
  - Handles user input and executes corresponding memory operations.
