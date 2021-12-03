# RISC-V_code

## What is RISC-V

- open standard ISA based on RISC principals
- open sourced, deployable in any hardware or software.
- ARM and x86 charge royalaties.


## Architecture

- 32bit, 64bit & 128bit implementations.
- 33 registers including $PC , 32 general
	- x0-x31+pc

- Given seperate identifiers based on use in the RISCV calling convention (x0 = zero, x1 = ra)
	- 6 general purpose
	- 7 temperary(t0-t6)  - data doesnt persist
	- 12 saved (s0-s11) - non volatile
	- 8 argument(a0-a7) - 

## Instruction template

Three register

	<operation>	<dst>,<src1>,<src2>

- addi a2,x0,64
	- $a2 = $zero + 64
	- $a2 = 64

- la a1, helloworld
	- a1 = address of helloworld label


## RISC-V syscall table

- To do anything have to ask kernel for help

- Linux syscall table defines how to interact with the kernel.
	- Specifies functions, syscall numbers, arguments required , etc.

- For ex:- exit syscall 93, write syscall 64

### Implementing a syscall

	- Set a7 to syscall number
	- Set a0 .. to arguments
	- Invoke the ecall instruction to call the kernel

System sysscall numbers 
[https://github.com/westerndigitalcorporation/RISC-V-Linux/blob/master/linux/include/uapi/asm-generic/unistd.h]

## Setup

sudo apt install gcc-riscv64-linux-gnu



