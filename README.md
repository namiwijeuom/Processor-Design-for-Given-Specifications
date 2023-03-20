# Processor Design for Given Specifications #
This is another group project done under the module, EN2031 - Fundamentals of Computer Organization and Design in the third semester of the Department of Electronic and Telecommunication Engineering of University of Moratuwa, Sri Lanka.

The following task was assigned to us.

A custom processor is to be designed for a computational unit and it will be part of a System on Chip (SoC) to be placed in an embedded system for a high-speed Industry 4.0 compliant factory operation. The decision on a custom processor was made following an in-depth investigation which reveals that off-the-shelf
embedded processors do not meet the throughput requirements.

The processor is not expected to run an operating system. A custom compiler will convert C language program to assembly which will be loaded to program memory. Pipeline processing is required to achieve the required throughput.

Following are the given specifications of the processor.

- Data Memory and Program Memory to be of size 64KB (high speed low latency) and the memory is dual port. Both Program and Data Memory can handle 16-bit words.
- A registry file R contains 8 registers : R0 to R7 where R7 acts as a Stack Pointer.
- Program Counter (PC) is considered as a special register.
- SREG is a special circular buffer that holds 8 1-bit values corresponding to results of evaluated condition in branch instructions.
- 16-bit Arithmetic and Logic Unit (ALU).
- Dedicated adders are to be used for address incrementing/decrementing where appropriate.
- Data Memory has an area reserved for a stack (limited to 4KB) and Data Memory is accessed by a separate 16-bit address bus.
- Load instructions have different variants as given below under Instruction Set details.
- The instruction set supports the following:
  - Arithmetic instructions on the ALU. The supported operations are addition, subtraction, bitwise AND and bitwise OR.
  - Any register in the registry file can be selected either as an operand or a result register. The selection of the one operand register and the result register must be identical. This is referred to as read-modify-write constraint.
  - POP from and PUSH to the Stack. SP is decremented/incremented as part of POP/PUSH instruction using an ALU.
  - Indirect register load from Data Memory. Every register in the Registry file can be specified as an address register and as a destination register. Hint: If Data Memory is DM, Rd=DM[Ra]. where Rd and Ra are any of the registers in Register File R except R7 – Stack Pointer.
  - Indirect register load from Data Memory with address post-modification. Every register in the
Registry file can be specified as an address register and as a destination register. In parallel with
the load, the address register is incremented on the ALU (read-modify-write constraint).
  - Instruction set needs to facilitate saving a 16-bit value to any register in R.
  - Data transfer between any two registers in R.
  - Unconditional and conditional branch instructions. The target address is specified relative to the current program counter value. It is supplied as an 8-bit signed immediate value.
  - Conditional branch instructions do register comparisons for equality, less than or equal and greater than or equal conditions. The evaluated conditions are stored in SREG. [Hint: Consider using one register in the Registry file R designated as one register for branch condition comparison
purposes]
  - 8-bit load immediate instruction. An 8-bit signed constant is loaded to any register. 8-bit immediate value is signed extended to a 16-bit value.
