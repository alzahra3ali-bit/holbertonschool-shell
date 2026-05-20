# The Simple Shell Project

A custom lightweight UNIX command-line interpreter written in C, built as part of the low-level programming curriculum.

The Simple Shell is a foundational system-level project that replicates the essential functionalities of the standard /bin/sh shell. It interfaces directly with the Linux kernel via system calls to manage processes, handle user inputs, navigate the environment, and execute binaries.

---

## Design Principles

Our implementation is guided by strict system programming principles, aiming to be stable, leak-free, and compliant with standard POSIX behaviors.

* Process Isolation: Every command execution is safely isolated inside a child process using fork and execve, ensuring the main shell process never crashes on command failures.
* Efficient Memory Management: The shell ensures clean termination with absolute zero memory leaks, strictly freeing all dynamically allocated blocks (malloc, getline, strtok).
* Resource Optimization: System calls are invoked judiciously and only when necessary to balance performance and kernel overhead.
* Compliance & Style: All source files strictly adhere to the Betty coding and documentation standards.

---

## Audience & Purpose

This project is created for educational and systems-engineering exploration. It is designed to demonstrate a deep, ground-up understanding of how operating systems handle process creation, memory allocation, context switching, and path resolution without relying on modern high-level abstractions.

---

## Technical Specifications

### Compilation Requirements
All files are structured to compile seamlessly on Ubuntu 20.04 LTS using gcc with the following strict warning flags:
```bash
gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh
