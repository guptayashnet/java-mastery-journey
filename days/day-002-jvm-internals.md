# Day 2: Topic 1 — Java Fundamentals Deep Dive
**Topic:** JVM, JDK, JRE, Bytecode & Compilation Internals  
**Date:** 2026-10-27  
**Status:** Completed  

---

## 1. Summary of Architecture
- **JDK:** Development tools (`javac`, `javap`, `jcmd`) + Runtime environment.
- **JRE:** Runtime libraries + JVM.
- **JVM:** Execution engine, ClassLoader subsystem, and memory manager.

## 2. Compilation & Execution Pipeline
1. `javac` compiles source code into platform-neutral Bytecode (`.class`).
2. ClassLoader performs **Loading**, **Linking** (Verify, Prepare, Resolve), and **Initialization**.
3. Execution Engine executes via **Interpreter** and compiles hot paths using the **JIT Compiler**.

## 3. Bytecode Disassembly Example
Stack-based instruction flow:
```text
iload_0  -> push arg0
iload_1  -> push arg1
iadd     -> add top two stack items
istore_2 -> store result in local var 2
```

## 4. Key Traps Covered
- `NoClassDefFoundError` vs `ClassNotFoundException`.
- Static initializer exceptions causing permanent class loading failure.
- Package hierarchies and root classpath resolution.
