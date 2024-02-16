# Simple-CPU-Implementation
A Lab for ECE243


This Verilog code defines a simple processor module along with supporting modules. Let's break down the main module (proc) and the supporting modules (dec3to8 and regn):

proc Module:
This module represents a simple processor with the following components:

Inputs and Outputs:

Inputs: DIN (16-bit data input), Resetn (active low reset), Clock (system clock), Run (control signal), and Done (output signal).
Outputs: Done (indicating the completion of an instruction).
Registers:

BusWires: 16-bit register serving as the internal bus.
Rin: 8-bit register for selecting one of the eight general-purpose registers.
Sum: 16-bit register storing the result of arithmetic operations.
IRin, Ain, Gin, AddSub: Single-bit registers controlling various operations.
Tstep_Q, Tstep_D: 3-bit registers representing the current and next state of the control Finite State Machine (FSM).
Wires:

III, rX, rY: Wires for opcode and register operands.
Xreg: 8-bit wire for the selected register.
R0 to R7, A, G, IR: Wires representing different registers and inputs.
Parameters:

Opcode definitions (mv, mvt, add, sub).
Selector definitions for multiplexers (Sel_R0, Sel_R1, ..., Sel_D8).
Time step parameters (T0 to T3).
Control FSM:

State-based control for sequencing the processor operations.
Instruction Execution:

Logic for executing different instructions (mv, mvt, add, sub).
Selection of register operands and immediate values.
Control signals for various operations.
ALU:

Arithmetic Logic Unit for performing arithmetic operations (+ or -).
Output (Sum) depends on the selected operation (AddSub).
Internal Processor Bus:

Multiplexer logic for selecting data from various sources (R0 to R7, G, immediate data).
Output (BusWires) feeds into the ALU and registers.
