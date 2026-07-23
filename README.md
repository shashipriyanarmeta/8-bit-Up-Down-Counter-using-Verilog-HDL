# 8-bit-Up-Down-Counter-using-Verilog-HDL


An 8-bit Up-Down Counter implemented in Verilog HDL, which increments or decrements based on a mode-select input — simulated and synthesized on Xilinx Vivado.

## Aim of the Project
To design and implement an 8-bit Up-Down Counter using Verilog HDL, which counts upward or downward on each positive clock edge based on a mode-select input, with a synchronous reset feature.

## Software Used
- **Xilinx Vivado Design Suite** (for simulation, synthesis, and implementation)
- Verilog HDL for RTL coding

## Purpose
The purpose of this project is to understand the design and functioning of sequential circuits, specifically how a single control signal (`mode`) can be used to make a counter operate bidirectionally. It also demonstrates how RTL code gets synthesized into actual hardware components (adder, subtractor, multiplexer, and register) on an FPGA.

## Working
- The counter is an 8-bit register (`y`) that updates on every **positive edge of the clock**.
- **Reset (`rst`):** When `rst = 1`, the counter output `y` is cleared to `0`.
- **Mode Selection:**
  - When `mode = 1`, the counter increments (`y = y + 1`) on each clock pulse → **Up-Counting**.
  - When `mode = 0`, the counter decrements (`y = y - 1`) on each clock pulse → **Down-Counting**.
- The synthesized schematic shows the RTL blocks generated: an **adder**, a **subtractor**, a **multiplexer** (to select between add/subtract based on `mode`), and a **register** (to hold and update `y` on the clock edge, with reset control).
- Being 8-bit wide, the counter counts from `0` to `255` in up mode and wraps around after reaching the limit in either direction.

## Simulation Results
- **Up-Counting Mode (`mode = 1`):** The output `y` increments by 1 on every clock cycle.
- **Down-Counting Mode (`mode = 0`):** The output `y` decrements by 1 on every clock cycle.

## Advantages
- Simple and easy to implement using minimal logic.
- Single control signal (`mode`) allows both counting directions without separate modules.
- Synchronous design ensures stable, predictable operation and easy timing analysis.
- Scalable — can be easily extended to more bits (16-bit, 32-bit, etc.) by changing the register size.
- No external components required — fully implemented in hardware logic.

## Applications
- Digital clocks and timers
- Frequency dividers
- Event counters in industrial automation
- Memory address generators in digital systems
- Traffic light controllers (for countdown/count-up timing)
- Elevator floor counters
- ADC/DAC control systems requiring sequential counting
