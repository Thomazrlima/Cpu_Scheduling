<p align="center">
  <img
    src="https://img.shields.io/badge/Status-Finalizado%20-green?style=flat-square"
    alt="Status"
  />
</p>

<p align="center">
  <img
    src="https://img.shields.io/github/repo-size/Thomazrlima/Cpu_Scheduling?style=flat"
    alt="Repository Size"
  />
  <img
    src="https://img.shields.io/github/languages/count/Thomazrlima/Cpu_Scheduling?style=flat&logo=python"
    alt="Language Count"
  />
  <img
    src="https://img.shields.io/github/commit-activity/t/Thomazrlima/Cpu_Scheduling?style=flat&logo=github"
    alt="Commit Activity"
  />
  <a href="LICENSE.md"
    ><img
      src="https://img.shields.io/github/license/Thomazrlima/Cpu_Scheduling"
      alt="License"
  /></a>
</p>

# CPU Scheduling Simulation

## 👀 Overview
This project implements the Rate-Monotonic (rate) and Earliest-Deadline-First (edf) algorithms for simulating real-time systems. The program reads task information from an input file and schedules them based on the specified algorithms.

## 📬 Input File Format

The input file should have the following format:

    [TOTAL TIME]
    [TASK NAME 1] [PERIOD 1] [CPU BURST 1]
    [TASK NAME 2] [PERIOD 2] [CPU BURST 2]
    ...
    [TASK NAME n] [PERIOD n] [CPU BURST n]


- `[TOTAL TIME]`: Total simulation time.
- `[TASK NAME i]`: Name of the i-th task.
- `[PERIOD i]`: Period of the i-th task.
- `[CPU BURST i]`: CPU burst time for the i-th task.

## 🪛 Build Instructions

1. Ensure you are on a Linux, Unix, or macOS system.
2. Compile using `make` with the desired algorithm name as a parameter:
   - `make rate` for Rate-Monotonic.
   - `make edf` for Earliest-Deadline-First.
   
## 📎Execution

Run the compiled executable with the input file:
- For Rate-Monotonic: `./rate [input_file]`
- For Earliest-Deadline-First: `./edf [input_file]`

## 📜 Specifications and Notes

1. The program is written in C and compiled using a Makefile.
2. Input files must not have a blank line at the end, and each line must not have extra spaces between task parameters.
3. Tasks described in the input file arrive simultaneously at time 0 for execution.
4. Priorities are resolved using the FCFS algorithm in case of tie.
5. If a task finishes exactly when a higher-priority task arrives, the lower-priority task is considered finished.
6. Tasks arriving exactly at the simulation end are marked as KILLED.
7. Zero CPU bursts or missed tasks with zero execution units do not need to be displayed.
8. Priority calculation for rate and edf algorithms is based on the specified task period as the deadline.

## 📩 Example Input

For example, given an input file named `input.txt` with the following content:

    165
    T1 50 25
    T2 80 35

## 📦 Output File

The output file format follows strict guidelines as provided in the assignment.

    EXECUTION BY RATE
    [T1] for 25 units - F
    [T2] for 25 units - H
    [T1] for 25 units - F
    [T2] for 5 units - L
    [T2] for 20 units - H
    [T1] for 25 units - F
    [T2] for 15 units - F
    idle for 10 units
    [T1] for 15 units - K
    LOST DEADLINES
    [T1] 0
    [T2] 1
    COMPLETE EXECUTION
    [T1] 3
    [T2] 1
    KILLED
    [T1] 1
    [T2] 1

## 👨‍👩‍👧‍👦 Contribuintes
  
<a href="https://github.com/Thomazrlima/Cpu_Scheduling/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=Thomazrlima/Cpu_Scheduling" />
</a>

## ⚖️ License

[MIT](https://github.com/Thomazrlima/Cpu_Scheduling/blob/master/LICENSE)
