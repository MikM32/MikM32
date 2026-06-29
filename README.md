

**Languages — in order of how close they sit to the hardware:**

```
x86 / x86-64 Assembly   ████████████████████  the ground floor
C                       ███████████████████░  one step above bare metal
C++                     ████████████████░░░░  when I need abstractions I control
Rust                    ██████████████░░░░░░  systems safety without the compromise
Python                  ████████████░░░░░░░░  fast prototyping, tooling, automation
```

- **Reverse Engineering** — static and dynamic analysis, binary unpacking, protocol reversing
- **Low-level systems** — memory layout, calling conventions, linkers, loaders, ELF/PE internals
- **Compilers & runtimes** — how high-level constructs collapse into instructions

---

## Tools I trust

| Category | Tools |
|---|---|
| Disassemblers | IDA Pro, Ghidra, radare2 |
| Debuggers | GDB + pwndbg/peda, x64dbg, WinDbg |
| Dynamic analysis | Frida |
| Build & link | NASM, MASM, GCC, ld, objdump, readelf |

---

## How I think about software

Most bugs are not logic errors. They are memory errors — an off-by-one in a boundary check, a dangling pointer, a race between threads, a signed/unsigned mismatch that only matters at 0x7fffffff. I've learned to read code the way a CPU reads it: linearly, ruthlessly, without assumptions.

I believe that understanding what happens **below** your abstraction layer makes you a better programmer **at** your abstraction layer. You write better Python when you know what `malloc` does. You write better Rust when you understand what the borrow checker is protecting you from at the instruction level.


If you think assembly is dead, I will politely disagree and show you why the compiler was wrong.

---

```asm
section .lol
    mov  rax, 0xDEADBEEF
    mov  rbx, 0xBADF00D
    xor  rcx, rcx          ; .l.
    call pelar_balls
```

<p align="center">
  <img src="https://img.shields.io/badge/Assembly-x86__64-6E4C13?style=flat-square&logo=assemblyscript&logoColor=white"/>
  <img src="https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white"/>
  <img src="https://img.shields.io/badge/C++-004482?style=flat-square&logo=cplusplus&logoColor=white"/>
  <img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Reverse%20Engineering-RE-8B0000?style=flat-square"/>
  <img src="https://img.shields.io/badge/GDB-darkgreen?style=flat-square"/>
  <img src="https://img.shields.io/badge/Ghidra-red?style=flat-square"/>
</p>

