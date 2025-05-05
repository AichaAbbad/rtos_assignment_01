# 🧵 Multithreaded Application with Custom Driver

## Overview

This project demonstrates a multithreaded application with:

- **Three periodic threads**:
  - `J1` – period: **300 ms**
  - `J2` – period: **500 ms**
  - `J3` – period: **800 ms**

- **One aperiodic thread (`J4`)**, which is triggered by `J2`.

A minimal **custom character driver** is also implemented, supporting basic operations: `open`, `write`, and `close`.

---

## 🧠 Thread Behavior

Each thread executes the following sequence:

1. **Open** the special file associated with the driver.
2. **Write** its identifier with an **opening bracket** (`[1`, `[2`, `[3`, or `[4`).
3. **Close** the special file.
4. **Waste time** to simulate workload.
5. **Open** the special file again.
6. **Write** its identifier with a **closing bracket** (`1]`, `2]`, `3]`, or `4]`).
7. **Close** the special file.

---

## 🛠 Driver Functionality

The custom character driver implements:

- `open()` – Prepares the driver to receive input.
- `write()` – Logs the thread's identifier with brackets.
- `close()` – Cleans up the session.

All output is logged via `dmesg` or a user-defined log mechanism.

