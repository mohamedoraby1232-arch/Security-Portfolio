# 🛡️ Security Portfolio: Low-Level Analysis & Reverse Engineering

Welcome to my cybersecurity portfolio. This repository documents my hands-on journey into low-level memory analysis, exploitation, and reverse engineering, all performed directly from an Android device using Termux.

## 🛠️ Technologies & Tools Used
- **Languages:** C, ARM64 Assembly.
- **Environment:** Termux (Android), Clang Compiler, Termux:X11.
- **Security Tools:** GDB (GNU Debugger), Ghidra.

---

## 📂 Project 1: C Memory Analysis & Scoping
**Folder:** `01_C_Memory_Analysis`
I analyzed how C manages memory, specifically the difference between the **Stack** (local variables) and the **Data Segment** (global variables).

### Key Achievements:
- Wrote C scripts (`scope3.c`) to track memory addresses using the `%p` format specifier.
- Proved that local variables get new memory addresses in the stack for each function call, while global variables maintain a static address in memory.
- Demonstrated how local variables "shadow" global variables within their function scope.

## 💥 Project 2: GDB Exploitation & Control Flow Hijacking
**Folder:** `02_GDB_Exploitation_Logs`
I intentionally caused Segmentation Faults and used GDB to analyze the crash and manipulate program execution.

### Key Achievements:
- Analyzed the `where` backtrace to track the function call stack (`main -> func1 -> func2 -> func3`).
- Successfully executed a **Control Flow Hijack**: manually altered the Program Counter (`$pc`) register to force the program to jump directly into `main` without properly returning from `func3`.
- *See `GDB_Analysis_Log.txt` for the full terminal transcript of the exploitation process.*

## 🕵️ Project 3: Android libc.so Reverse Engineering
**Folder:** `03_Ghidra_Reverse_Engineering`
I extracted the Android C library (`libc_copy.so`) and analyzed it using Ghidra via Termux:X11 (running a graphical interface on Android).

### Key Achievements:
- Successfully ran Ghidra on an Android device without a PC.
- Disassembled the internal `atoi` function (mangled as `StrToI` in C++).
- Observed the ARM64 Assembly instructions (e.g., `mov w2, #0xa`) and analyzed how the base-10 conversion is handled at the hardware level.

---
*This portfolio is continuously updated as I explore more about cybersecurity, memory exploitation, and reverse engineering.*
