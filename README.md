# OS Concepts Simulator — System Calls & MMU

This repository contains two modules I individually developed as part of a larger **group Operating System simulator project** (team of 10, [original repo](https://github.com/Master9Wayne/OS-EMULATOR-T9)). The full project simulates many OS concepts (scheduling, deadlock detection, file systems, IPC, etc.) across separate modules built by different team members. This repo includes **only the modules I built**.

## My Modules

### 1. System Calls (`system-calls/`)
A simulated shell/terminal demonstrating how system calls bridge user-mode programs and kernel-mode services.

- Implements a central syscall dispatcher (`handleSystemCall`) that routes commands to handlers
- Simulated calls: `open`, `read`, `write`, `close`, `fork`, `exec`, `exit`, `malloc`, `free`, `switch`
- Maintains simulated kernel state: process table, open file descriptor table, and a memory map
- Animates the user-mode → kernel-mode → user-mode transition for each call to visualize context switching

### 2. MMU — Memory Management Unit (`MMU/`)
An interactive simulator for virtual-to-physical address translation, supporting two memory management schemes:

- **Segmentation**: maintains a segment table (Code, Data, Stack, Heap) with base/limit pairs; translates `(segment, offset)` to a physical address and detects segment violations when the offset exceeds the limit
- **Paging**: maintains a page table mapping 16 pages to 32 physical frames, including valid/invalid bits; translates `(page, offset)` to a physical address and simulates page faults for invalid pages
- Visualizes virtual and physical memory layouts side by side with animated address translation

## Tech Stack
HTML, CSS, JavaScript (vanilla, DOM-based simulation and visualization)

## Note on Scope
This was a collaborative class/group project. The modules above represent my individual contribution; other modules (scheduling, deadlock, file allocation, IPC, etc.) were built by teammates and are part of the full team repository linked above.
