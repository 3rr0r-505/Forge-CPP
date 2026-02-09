# ⚙️ HexHound — C++ MALWARE ANALYSIS SIMULATOR

## ⁉️ Project Title  

### Basic Malware Behavior Analysis & Logging System

## 🎯 Objective  

Build a **console-based C++ program** that simulates how a malware analysis tool:
- collects behavior data
- evaluates severity
- handles malformed inputs
- stores results
- logs execution safely

This project integrates **all major C++ concepts learned from W3Schools** without going into advanced exploitation or OS internals.

## 📜 Project Description  

You are building a **basic malware analysis simulator**.

The program accepts multiple malware behavior records, analyzes them, assigns risk levels, stores them using STL containers, and logs results to a file with timestamps.

The system must be **robust**, **well-structured**, and **safe against invalid input** — just like real malware analysis tools.

## 🧩 Core Features & Concept Mapping  

### 🔹 C++ Basics
- Variables, data types, operators
- User input & output
- Strings, math, booleans
- If-else, switch
- Loops (for / while)
- Break & continue

### 🔹 Arrays, Structs, Enums
- Array / vector to store behaviors
- `struct` for MalwareRecord
- `enum` for RiskLevel

### 🔹 References & Pointers
- Pass records using references
- Use pointers for dynamic memory storage

### 🔹 Memory Management
- Allocate malware records dynamically
- Free memory safely

### 🔹 Functions
- Modular analysis functions
- Function overloading (log output)
- Recursion (optional severity scan)
- Lambda for filtering high-risk malware

### 🔹 OOP (Classes)
- Base class: `MalwareComponent`
- Derived classes:
  - `Keylogger`
  - `NetworkBeacon`
  - `PersistenceMechanism`
- Constructors & encapsulation
- Polymorphism via base-class pointers
- Templates for logging
- File handling
- Date & time tracking

### 🔹 Errors & Validation
- Input validation
- Exception handling
- Safe error recovery (no crash)

### 🔹 STL & Algorithms
- `vector` → execution trace
- `set` → unique components
- `map` → component → severity
- `stack` → simulated call stack
- `queue` → scheduled tasks
- Algorithms: `max_element`, `find`, `count`

### 🔹 Namespaces
- `Analysis`
- `Logger`
- `Utils`

## 📐 Rules & Logic  

### Malware Severity Rules

| Component | Base Severity |
|---------|---------------|
| Keylogger | 4 |
| NetworkBeacon | 3 |
| PersistenceMechanism | 5 |

### Risk Classification
- Severity ≥ 6 → `DANGEROUS`
- Severity 3–5 → `MODERATE`
- Severity ≤ 2 → `LOW`

### Validation Rules
- Invalid component name → reject
- Severity < 0 → invalid
- Severity > 10 → suspicious overflow
- Program must continue after errors

## 🚦 Program Output  

For each malware record:
- Component name
- Severity
- Risk level
- Timestamp
- Logged to file

Also display:
- Execution order
- Unique components detected
- Highest-risk component

## 🧪 Test Cases  

| Test Case | Category | Input |
|----------|----------|-------|
| 1 | Normal | `n=2; Keylogger 4, NetworkBeacon 3` |
| 2 | Normal | `n=3; NetworkBeacon 3, PersistenceMechanism 5, Keylogger 4` |
| 3 | Normal | `n=1; PersistenceMechanism 5` |
| 4 | Edge | `n=0` |
| 5 | Edge | `n=1; Keylogger 6` |
| 6 | Edge | `n=1; NetworkBeacon -1` |
| 7 | Edge | `n=2; Keylogger 2, PersistenceMechanism 7` |
| 8 | Edge | `n=3; Keylogger 10, NetworkBeacon 10, PersistenceMechanism 10` |

## 📊 Expected Outcomes Summary  

| Test Case | Expected Outcome |
|----------|------------------|
| 1 | MODERATE highest risk |
| 2 | DANGEROUS highest risk |
| 3 | DANGEROUS |
| 4 | No data handled safely |
| 5 | DANGEROUS |
| 6 | Invalid input handled |
| 7 | DANGEROUS |
| 8 | All high-risk components |

## 📁 Output File Example  
[2026-02-09 16:20:10] Keylogger 4 MODERATE
[2026-02-09 16:20:10] NetworkBeacon 3 MODERATE
