
# Samsung RISC-V


![gatworkshop](https://github.com/user-attachments/assets/9fd60b88-75be-4401-8961-ba5d76e43e77)

![gatworkshop1](https://github.com/user-attachments/assets/78df1db3-0caa-4937-b907-bc7349ba9f29)

![gatworkshop](https://github.com/user-attachments/assets/77d7ecbe-0659-4832-a9ae-5750204f77d8)

![gatworkshop2](https://github.com/user-attachments/assets/a44507e8-49c8-466a-8709-0c755cfd6ba3)

![gatworkshop3](https://github.com/user-attachments/assets/a3e874f8-c020-46c3-b2e8-b453325f3d78)

![gatworskshop4](https://github.com/user-attachments/assets/ac145e09-647f-4b5b-87ac-fb0f2492d3a4)

# Task 1:

![c based lab](https://github.com/user-attachments/assets/919edf97-b9d1-4f6c-8f3a-56706c8957f5)

![task1](https://github.com/user-attachments/assets/8522036a-81b9-4154-9fa5-ddb490c155d3)

![task1-2](https://github.com/user-attachments/assets/ac24a7d2-a901-43d3-8835-26d67f7e3d61)

![task1-3](https://github.com/user-attachments/assets/291c307a-c25a-4204-b233-8841f4c25305)


# Task 2

![risc-v lab](https://github.com/user-attachments/assets/8058a505-1217-4a6f-9978-c69832515136)

![RISC-V 2](https://github.com/user-attachments/assets/2417a512-db67-4cbd-88af-a39c8806e51d)

![spike simulation](https://github.com/user-attachments/assets/69c2520d-6a62-4d64-bf57-b7390070c07a)

![spike simulation  -o1](https://github.com/user-attachments/assets/78c890ea-04ab-427d-8296-2e770795965a)

![object dump -ofast](https://github.com/user-attachments/assets/fde61ccb-cfbc-4939-a82d-af101d61a38c)

![object dump -o1](https://github.com/user-attachments/assets/a61adc52-62ad-4a07-b2d8-160035eb2414)


# Task 3

The R,I,S,B,U and J instruction types are commonly used in RISC(Reduced
 instruction set computing)architectures,such as MIPS or RISC-V,and help in defining how instructions are encoded and processed by the CPU.
RISC-V RV32 refers to a 32-bit RISC-V 
the RISC-V RV32 instruction set has 6 main instructions types,based on their encoding format.These types are determined by how operands and immediate values are encoded in the instruction.The six instructions types are:

1. R-Type(Register Type)
2. I-Type(Immediate Type)
3. S-Type(Store Type)
4. U-Type(Branch Type)
5. B-Type(Upper Immediate Type)
6. J-Type(Jump Type)

RISC-V Instruction Sets

![image](https://github.com/user-attachments/assets/0ad2f314-8dee-45d5-b522-672b4713142b)

# 1.R-Type(Register Type)

The R-Type instruction format in RISC-V is designed to perform register-to-regsiter operations.each field has a specific role,contributing to the functionality and flexibility of the instructions.Here's a detailed breakdown of eacg field:

   - Opcode (7 bits)

     Identifies the broad category of the instruction (e.g., arithmetic, logical, shift). The opcode determines the type of operation and the instruction format (e.g., R- type, I-type, S-type).

     Placement: Bits [6:0].

     Examples: 0110011: R-type operations (add, sub, and, or, etc.).

  - rd (Destination Register, 5 bits)

     Specify the register where the result of the operation will be stored.

     Placement: Bits [11:7].

     The register index ranges from 0 to 31, corresponding to the 32 general-purpose registers in RISC-V (e.g., x0 to x31). Writing to x0 is effectively a NOP (writes are ignored since x0 is hardwired to 0).

     Example: If rd = 01010, it means the result is stored in register x10.

  - rd (Destination Register, 5 bits)

     Specifies the specific operation to be performed within the instruction category defined by opcode.

     Placement: Bits [14:12]. funct3 works in combination with funct7 to differentiate between similar operations. Common values: 000: Add or subtract (depending on funct7). 111: AND operation. 110: OR operation.

     Examples: For an ADD instruction: funct3 = 000. For an AND instruction: funct3 = 111.

  - rs1 (Source Register 1, 5 bits)

     Specifies the first source register containing one of the operands.

     Placement: Bits [19:15].

    The register index ranges from 0 to 31, like rd. It holds the value used in computation or logical operation.

     Example: If rs1 = 00001, it means the first operand is in register x1.

 - rs2 (Source Register 2, 5 bits)

     Specifies the second source register containing the second operand.

     Placement: Bits [24:20].

    Like rs1, the register index ranges from 0 to 31. It provides the second value used in computations.

    Example: If rs2 = 00010, it means the second operand is in register x2.

 - funct7 (Function Code, 7 bits)

     Provides additional specificity to distinguish between operations that share the same opcode and funct3.

     Placement: Bits [31:25].

     This field is essential for certain instructions with similar opcode and funct3 but different behaviors. Common values: 0000000: Standard operation (e.g., add). 0100000: Alternative operation (e.g., sub).

     Examples: For ADD: funct7 = 0000000. For SUB: funct7 = 0100000.

 
# 2.The I-Type(Immediate-Type)

The I-type (Immediate-type) instruction format in RISC-V is used for instructions that operate on one register operand and an immediate value. These instructions are common for operations such as memory access, arithmetic with constants, or conditional jumps. The I-type format has the following fields:

  - opcode (7 bits): Identifies the type of instruction (e.g., arithmetic, memory access, etc.).

      Placement: Bits [6:0].

      Common opcodes for I-type: 0000011: Load instructions (e.g., lw for load word). 0010011: Arithmetic instructions with an immediate (e.g., addi).

 - rd (Destination Register, 5 bits): Specifies the destination register where the result of the operation will be stored. Placement: Bits [11:7]. Holds the result of the operation (e.g., the value loaded from 
       memory or the result of arithmetic with the immediate). Example: If rd = 00010, the result is written to register x2.

 - funct3 (Function Code, 3 bits): Specifies the specific operation within the instruction type.

      Placement: Bits [14:12].

      Differentiates between operations like addi, slti, or load instructions like lb (load byte), lw (load word).

      Examples: 000: Add immediate (addi). 010: Set less than immediate (slti). 100: XOR immediate (xori).

  - rs1 (Source Register 1, 5 bits): Specifies the register providing the first operand.

       Placement: Bits [19:15].

      The value in this register is combined with the immediate value (imm) in the specified operation.

      Example: If rs1 = 00001, it means the value in register x1 is used as the operand.

  - imm (Immediate Value, 12 bits): Provides a constant value or offset for the instruction.

       Placement: Bits [31:20].

      Signed 12-bit value (using two's complement). Can represent values in the range of -2048 to 2047. Zero-extended or sign-extended as needed based on the operation. Used for: Arithmetic operations (e.g., 
      addi adds rs1 and imm). Load instructions (e.g., memory address is rs1 + I'm).

      Examples: For addi x3, x2, 10: imm = 10 (decimal). For lw x5, 100(x1): imm = 100 (offset).

# 3. The S-type (Store-type)

   The S-type (Store-type) instruction format in RISC-V is designed for instructions that store data from a register in memory. It uses a combination of a base address from one register and an immediate 
      offset to calculate the effective memory address.

   The S-type format has the following fields:

  - opcode (7 bits): Identifies the type of instruction (store in this case).

      Placement: Bits [6:0].

      The common opcode for S-type instructions: 0100011: Store instructions (e.g., sw, sh, sb).

      Example: For a store word (sw) instruction: opcode = 0100011.

  - imm (Immediate Value, 12 bits total): Specifies the offset to be added to the base address in rs1 to calculate the effective memory address.

       Placement: Upper 7 bits (imm[11:5]): Bits [31:25]. Lower 5 bits (imm[4:0]): Bits [11:7].

      Immediate is a signed 12-bit value (using two's complement).Can represent offsets from -2048 to 2047. The two parts (imm[11:5] and imm[4:0]) are combined during instruction decoding to form the complete immediate.

       Example: If imm[11:5] = 0000001 and imm[4:0] = 01010, the full immediate is 000000101010 (42 in decimal).

  - rs2 (Source Register 2, 5 bits): Specifies the register holding the data to be stored in memory.

    Placement: Bits [24:20].

    The contents of this register are written to the memory address calculated from rs1 + imm.

     Example: If rs2 = 00010, the data to be stored comes from register x2.

  - rs1 (Source Register 1, 5 bits): Specify the register holding the base address for memory access.

      Placement: Bits [19:15].

      The effective memory address is calculated as rs1 + imm.

      Example: If rs1 = 00001, the base address comes from register x1.

  - funct3 (Function Code, 3 bits): Specifies the type of data to be stored (e.g., byte, half-word, word).

      Placement: Bits [14:12].

      Determines the size of the data being stored. Common values: 000: Store byte (sb). 001: Store half-word (sh). 010: Store word (sw).

      Example: For a store word instruction: funct3 = 010.

# 4. The U-type instruction 

The U-type instruction format in the RISC-V architecture is used primarily for instructions that involve immediate values, typically for forming larger constants or calculating addresses. The U-type format is part of the 32-bit RISC-V instruction set. The U-type instruction has the following 32-bit structure:

  - Immediate (31–12):

       This is a 20-bit field that provides the upper 20 bits of a constant or address. The value is sign-extended when needed. The lower 12 bits are typically assumed to be zeros.

  - Destination Register (rd) (11–7): Specifies the register where the result of the instruction will be stored.

  - Opcode (6–0): Identifies the specific instruction. For U-type, common opcodes are: LUI (Load Upper Immediate): Opcode 0110111. AUIPC (Add Upper Immediate to PC): Opcode 0010111.

# 5. The B-type (Branch-type)

The B-type(Branch-type)instruction format in RISC-V is designed for conditional branch instructions that control the flow of execution based on a comparison
between two registers. These instructions are typically used to implement if-else conditions, loops, and other control flow operations. The B-type format has the following fields:

  - opcode (7 bits): Identifies the type of instruction (branch in this case).

      Placement: Bits [6:0].

      The opcode for B-type instructions is 1100011. This indicates that the instruction is related to branching.

      Example: For a branch instruction: opcode = 1100011.

  - imm (Immediate Value, 13 bits): Provides the offset that is added to the program counter (PC) when the branch condition is met. This offset is calculated relative to the next instruction (PC + 4).

     Placement: imm[12]: The most significant bit (bit 12). imm[10:5]: Bits [10:5] for the middle 6 bits. imm[4:1]: Bits [4:1] for the least significant 4 bits. imm[11]: The second most significant bit (bit 11).

     The immediate value is signed (using two's complement) and is used to calculate the address of the target instruction. The immediate is shifted left by 1 bit during instruction decoding to account for word- 
      aligned addresses.

      Example: If imm[12] = 0, imm[10:5] = 000100, imm[4:1] = 0101, and imm[11] = 1, the complete immediate would be 000100010101 (in binary), which is 0x115 (277 in decimal).

  - rs2 (Source Register 2, 5 bits): Specifies the second register that is compared to rs1 for the branch decision.

       Placement: Bits [24:20].

      The value in rs2 is compared with the value in rs1. This field is used in the comparison operation for the branch (e.g., beq, bne).

       Example: If rs2 = 00010, the second operand is x2.

  - rs1 (Source Register 1, 5 bits): Specifies the first register that is compared to rs2.

      Placement: Bits [19:15].

The value in rs1 is compared with the value in rs2. For a beq (branch if equal) instruction, if the values in rs1 and rs2 are equal, the branch is taken.

Example: If rs1 = 00001, the first operand is x1.

  - funct3 (Function Code, 3 bits): Specify the type of comparison (e.g., equal, not equal, greater than, etc.).

Placement: Bits [14:12].

The comparison determines whether the branch will be taken. Common values: 000: Branch if equal (beq). 001: Branch if not equal (bne). 100: Branch if less than (blt). 101: Branch if greater than or equal (bge). 110: Branch if unsigned less than (bltu). 111: Branch if unsigned greater than or equal (bgeu).\n Examples:

beq (branch if equal): funct3 = 000. bne (branch if not equal): funct3 = 001.

# 6.The J-Type(Jump-Type)

The J-type (Jump-type) The J-type (Jump-type) instruction format in RISC-V is designed for unconditional jump operations. These instructions allow the program to change its execution flow by jumping to an address specified by a 12-bit signed immediate value. The immediate value is used to calculate the target address relative to the current Program Counter (PC).

Placement: Bits [19:15].

The J-type format has the following fields:

  - opcode (7 bits): Identifies the type of instruction. In J-type, the opcode specifies that the instruction is a jump.

     Placement: Bits [6:0].

     The opcode for J-type instructions is always 1101111 (which indicates the jump instruction category).

      Example: For a jump instruction (jal or jalr), opcode = 1101111.

  - imm (Immediate Value, 21 bits total): Purpose: Specifies the offset to be added to the current Program Counter (PC) to calculate the target address.

       Placement: imm[20]: Most significant bit of the immediate value (bit 20). imm[10:1]: Middle 10 bits of the immediate value. imm[11]: Second most significant bit (bit 11). imm[19:12]: Lower 8 bits of the 
       immediate value.

       The immediate value is signed and used to calculate the target address relative to the current instruction. The immediate value is shifted left by 1 bit to account for the word-aligned address (because 
        instructions are 4 bytes in RISC-V). This offset allows the jump to be within a ±1 MiB range (a total of 2^20 bytes, or 2^18 words).

    Example: If imm[20] = 0, imm[10:1] = 0101010101, imm[11] = 1, and imm[19:12] = 10101010, the full immediate value would be 0101010101101010101 (in binary), which is 0x55555 (349525 in decimal).

  - rs1 (5 bits): Purpose: This field is not used in J-type instructions and is always 0. It is reserved for compatibility with other instruction formats.


# 32-bit instructions code

![RISC-V 2](https://github.com/user-attachments/assets/3c045f64-9889-43ea-8f53-f8bcc866483a)

1. lui a2,0x1
   
      - Opcode (7 bits): 0110111
      - rd (5 bits): 01010 — register a2
      - funct3: 000 — not used for lui because it's a U-type instruction.
      - rs1: not used for lui its a U-type instruction.
      - Immediate (20 bits of 0x1): 00000000000000000001 

          The 32-bit binary representation for the instruction lui a2,0x1 is:
          01101110101000000000000000000001

2. lui a0,0x21

      - Opcode(7 bites): 0110111 (for LUI instruction)
      - rd(5 bites): 01010 (register a0)
      - funct3: Not used in LUI, as it's a U-type instruction.
      - rs1: Not used in LUI, as it's a U-type instruction.
      - Immediate: 0000000000100001 (upper 20 bits of 0x21, shifted by 12 bits)

          The 32-bit representation of the instruction LUI a0, 0x21 is:
          0110111 01010 0000000000100001 000000000000

3. addi sp,sp,-16
   
      - Opcode(7 bites): 0010011 (for ADDI instruction)
      - rd(5 bites): 00010 (for sp, register 2)
      - funct3(3 bites): 000 (for ADDI)
      - rs1(5 bites): 00010 (for sp, register 2)
      - Immediate(12 bites): 111111111000 (two's complement binary representation of -16)

          The 32-bit binary representation of the instruction ADDI sp, sp, -16 is:
          0010011 00010 000 00010 111111111000

4. addi a2,a2,954

      - Opcode(7 bites): 0010011 (for ADDI instruction)
      - rd(5 bits): 01010 (for a2, register 10)
      - funct3(3 bites): 000 (for ADDI)
      - rs1(5 bites): 01010 (for a2, register 10)
      - Immediate(12 bites): 0000001110110010 (binary representation of 954)

          The 32-bit binary representation of the instruction ADDI a2, a2, 954 is:
          0010011 01010 000 01010 0000001110110010

5. li a1,100
   
      - Opcode (7 bits): 0010011
      - rd (5 bits): 01011 (for register a1)
      - funct3 (3 bits): 000 (for ADDI)
      - rs1 (5 bits): 00000 (for register x0)
      - Immediate (12 bits): 0000001100100 (binary for 100)

          The 32-bit binary representation of the pseudo-instruction LI a1, 100 (equivalent to ADDI a1, x0, 100) is:
          0010011 01011 000 00000 0000001100100

6. addi a0,a0,38

      - Opcode (7 bits): 0010011
      -  rd (5 bits): 01010 (for register a0)
      - funct3 (3 bits): 000 (for ADDI)
      - rs1 (5 bits): 01010 (for register a0)
      - Immediate (12 bits): 0000000011000000 (binary for 384)

           The 32-bit binary representation of the instruction ADDI a0, a0, 384 is:
           0010011 01010 000 01010 0000000011000000

7. sd ra,8(sp)

      - Opcode (7 bits): 0100011 (for SD instruction)
      - rs2 (5 bits): 00001 (for ra, register 1)
      - rs1(5 bites): 00010 (for sp, register 2)
      - funct3(3 bites): 011 (for SD)
      - Immediate (12 bites): 0000000 01000 (binary representation of 8)

           The 32-bit binary representation of the instruction sd ra,8(sp) is:
           0100011 00001 00010 011 0000000 01000

8. jal ra,1040c
   
      - Opcode (7 bites): 1101111 (for JAL instruction)
      - rd (5 bites): 00001 (for ra, register 1)
      - imm[20] (1 bit): 0 (highest bit of the immediate value)
      - imm[10:1] (10 bits): 0001101001 (middle 10 bits of the immediate value)
      - imm[11] (1 bit): 1 (the 11th bit of the immediate value)
      - imm[19:12] (8 bits): 01111100 (lowest 8 bits of the immediate value)

           The 32-bit binary representation of the instruction JAL ra, 1040c is:
           0 0001101001 1 01111100 00001 1101111

9. ld ra,8(sp)

      - Opcode (7 bits): 0000011 (for LD instruction)
      - rd (5 bits): 00001 (for ra, register 1)
      - funct3 (3 bits): 011 (for LD)
      - rs1 (5 bits): 00010 (for sp, register 2)
      - Immediate (12 bits): 000000001000 (binary representation of 8)
  
         The 32-bit binary representation of the instruction LD ra, 8(sp) is:
         0000011 00001 011 00010 000000001000
 
10. li a0,0

     - Opcode (7 bites): 0010011 (for ADDI instruction)
     - rd (5 bites): 01010 (for a0, register 10)
     - funct3 (3 bites): 000 (for ADDI)
     - rs1 (5 bites): 00000 (for x0, register 0)
     - Immediate (12 bites): 000000000000 (binary representation of 0)

         The 32-bit binary representation of the instruction LI a0, 0 (which is typically translated to ADDI a0, x0, 0) is:
         0010011 01010 000 00000 000000000000

11. addi sp,sp,16

       - Opcode (7 bits): 0010011 (for ADDI instruction)
       -  rd (5 bits): 00010 (for sp, register 2)
       - funct3 (3 bits): 000 (for ADDI)
       - rs1 (5 bits): 00010 (for sp, register 2)
       - Immediate (12 bits): 000000001000 (binary representation of 16)
   
           The 32-bit binary representation of the instruction ADDI sp, sp, 16 is:
           0010011 00010 000 00010 000000001000

12. ret
   
      - Opcode (7 bits): 1100111 (for JALR instruction)
      - rd (5 bits): 00000 (for x0, register 0)
      - funct3 (3 bits): 000 (for JALR)
      - rs1 (5 bits): 00001 (for ra, register 1)
      - Immediate (12 bits): 000000000000 (binary representation of 0)
  
          The 32-bit binary representation of the instruction RET (which is translated to JALR x0, ra, 0) is:
          1100111 00000 000 00001 000000000000

13. auipc a5,0xffff0
    
       - Opcode (7 bits): 0010111 (for AUIPC instruction)
       - rd (5 bits): 01111 (for a5, register 15)
       - Immediate (20 bits): 11111111111100000000 (binary representation of 0xffff0)

            The 32-bit binary representation of the instruction AUIPC a5, 0xffff0 is:
            0010111 01111 11111111111100000000

# Task 4:

Functional simulation of RISC-V instructions modeled as a Verilog netlist and observe the output waveforms using GTKWave.

In Verilog design workflows, simulations are typically executed using tools like Icarus Verilog. During these simulations, waveform data is captured in files such as Value Change Dump (VCD). These files record the state of signals over time and are later viewed using waveform viewers like GTKWave. This graphical visualization helps in analyzing signal transitions and verifying both the design's functionality and timing behavior.

Installing iverilog using command sudo apt install iverilog gtkwave
 1. Create a directory with your name using the command: mkdir <your_name>

 2. Use the touch command to create two Verilog files named impana_rv32i.v and impana_rv32i_tb.v:

 3. Copy the required Verilog code and testbench code from the reference GitHub repository into the respective files.

 4. Open the gtkwave using command gtkwave iiitb_rv32i.vcd
    
All the instructions in the given verilog file is hard-coded. Hard-coded means that instead of following the RISCV specifications bit pattern, the designer has hard-coded each instructions based on their own pattern. Hence the 32-bits instruction that we generated in Task-2 will not match with the given instruction.

                                                                                               
1. ADD R6, R2, R1  - 	Adds the values in R2 and R1,stores result in R6
   
      Standard RISC-VISA  -  32'h00110333
      Hard Coded ISA  -   32'h02208300
   
2. SUB R7, R1, R2	 -  Subtracts the value in R2 from R1, stores result in R7
 
      Standard RISC-VISA - 32'h402083b3
      Hard Coded ISA  -   32'h02209380
   
3. AND R8, R1, R3	 - Performs bitwise AND between R1 and R3, stores in R8
 
      Standard RISC-VISA -32'h0030f433
      Hard Coded ISA  - 32'h0230a400
   
4. OR R9, R2, R5	  - Performs bitwise OR between R2 and R5, stores in R9
 
      Standard RISC-VISA - 32'h005164b3
      Hard Coded ISA  -  32'h02513480
    
5. XOR R10, R1, R4	- Performs bitwise XOR between R1 and R4, stores in R10
 
     Standard RISC-VISA - 32'h0040c533
     Hard Coded ISA  -  32'h0240c500
    
6. SLT R1, R2, R4	 - Sets R1 to 1 if R2 < R4, else sets to 0
 
     Standard RISC-VISA  - 32'h0045a0b3
     Hard Coded ISA  -  32'h02415580
    
7. ADDI R12, R4, 5	- Adds immediate value 5 to R4, stores result in R12
   
     Standard RISC-VISA - 32'h004120b3
     Hard Coded ISA  -  32'h00520600

8. BEQ R0, R0, 15	 - Branches to offset 15 if R0 equals R0
              
     Standard RISC-VISA - 32'h00000f63
     Hard Coded ISA  -  32'h00f00002

9. SW R3, R1, 2	   - Stores word from R3 to memory address (R1 + 2)
        
     Standard RISC-VISA  - 32'h0030a123
     Hard Coded ISA  -  32'h00209181

10. LW R13, R1, 2	 -  Loads word from memory address (R1 + 2) into R13
      
     Standard RISC-VISA  - 32'h0020a6
     Hard Coded ISA  -  32'h00208681
   
11. SRL R16, R14, R2 -  Shifts R14 right by the value in R2, stores in R16
 
     Standard RISC-VISA - 32'h003023
     Hard Coded ISA  -  32'h00271803
    
12. SLL R15, R1, R2	 - Shifts R1 left by the value in R2, stores in R15
 
     Standard RISC-VISA - 32'h0097b3
     Hard Coded ISA  -  32'h00208783

# Verifying instructions using Gtkwave

1. ADD R6,R2,R1

   ![waveform_1](https://github.com/user-attachments/assets/976b5790-0be9-48fc-b803-367eececa5cc)

2. SUB R7,R1,R2
 
 ![waveform_02](https://github.com/user-attachments/assets/4ec7dddb-defa-4c5a-8358-c3cff91a744b)

3. AND R8,R1,R3

![waveform_03](https://github.com/user-attachments/assets/d216611f-99df-4ead-99f0-c7547225a66d)

4. OR R9,R2,R5

![waveform_04](https://github.com/user-attachments/assets/5270b222-e0c5-475f-9d8c-711c1044e1fc)

5. XOR R10,R1,R4

![waveform_05](https://github.com/user-attachments/assets/09102a4c-0bfe-4016-b262-4c9c1a1d4595)

6. SLT R11,R2,R4

![waveform_06](https://github.com/user-attachments/assets/e817face-1af3-45dc-99cb-2a06d57f259d)

7. ADDI R12,R4,5

![waveform_07](https://github.com/user-attachments/assets/c44a8731-cca2-4934-9ee4-c3f1604eb45b)

8. SW R3,R1,2

![waveform_08](https://github.com/user-attachments/assets/b194ab14-8421-4e0b-ac85-55e88168fc0f)

9. SRL R16,R14,R2

![waveform_09](https://github.com/user-attachments/assets/a08dde92-95b6-4c94-bf82-7c202ae90f02)

10. BEQ R0,R0,15

![waveform_10](https://github.com/user-attachments/assets/27e017ef-c0ac-48f9-9d2f-885297de2b75)

11. SLL R15,R1,R2

![waveform_11](https://github.com/user-attachments/assets/e8b59a13-2fc2-40a5-a8d0-2b4b608ebbf0)


# TASK 5 :

# DOCUMENTATION OF PROJECT :  Clock Divider Circuit using VSDminiquadron

This project involves designing a digital clock divider circuit using the VSDSquadron Mini board. The circuit functions to reduce the input clock signal frequency, generating lower frequency outputs essential for all integrated circuits designs.


# Components Required:
Power Supply VSDSquadron Mini FPGA Board Clock Source Breadboard Jumper Wires LEDs

VSDminiquadron Board: VSDSquadron, a cutting-edge development board based on the RISC-V architecture that is fully open-source. This board presents an exceptional opportunity for individuals to learn about RISC-V and VLSI chip design utilizing only open-source tools, starting from the RTL and extending all the way to the GDSII. The possibilities for learning and advancement with this technology are limitless.

![Screenshot_2-3-2025_13650_www bing com](https://github.com/user-attachments/assets/66ff85ac-e1c4-4438-b671-5ee2c17e78e7)

# Circuit Connection:
Input Clock Source to VSDminiquadron board: Connect the clock source to the clock input pin on the VSDSquadron Mini.

Output Pins: Configure multiple GPIO pins on the VSDminiquadron board as clock outputs.

Power and Ground: Connect the power supply and ground to the VSDminiquadron board

![circuit diagram](https://github.com/user-attachments/assets/27ee584f-43cd-48fa-82fd-8b7a949ce3b1)

# Program: Verilog code for clock divider

module clkDiv(

input clk, // Input clock signal

input reset, // Reset signal

output reg clk_o1

);

    reg [31:0] N1; //counter

    parameter DIV = 10_000_000; // Desired frequency

always @(posedge clk or posedge reset)

       begin

      if (reset) 
       
       begin

          N1 <= 0;
  
         clk_o1 <= 0;
  
       end 

      else

    begin

  if (N1 == DIV - 1) 
  
  begin
  
      N1 <= 0;
      
      clk_o1 <= ~clk_o1;
      
 end 
 
 else
 
 begin
 
      N1 <= N1 + 1;
      
      end

 end

end

endmodule

# program - LED on and off

#include <ch32v00x.h> #include <stdio.h> #include <debug.h>

#define clock_PIN GPIO_Pin_6 // PD6 #define LED_PIN GPIO_Pin_3 // PD3

void NMI_Handler(void) attribute((interrupt("WCH-Interrupt-fast"))); void HardFault_Handler(void) attribute((interrupt("WCH-Interrupt-fast"))); void Delay_Init(void); void Delay_Ms(uint32_t n);

void setup() { GPIO_InitTypeDef GPIO_InitStructure = {0}; // Structure variable used for GPIO configuration

    // Enable clock for GPIOD
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE);

    GPIO_InitStructure.GPIO_Pin = clock_PIN;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IN_FLOATING;  // Defined as Input Floating Type
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    // LED Pin Configuration as output push-pull

    GPIO_InitStructure.GPIO_Pin = LED_PIN;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;  // Defined as Output Push-Pull Type
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;  // Defined Speed
    GPIO_Init(GPIOD, &GPIO_InitStructure);

}

void loop() { // Check if sound sensor is triggered if (GPIO_ReadInputDataBit(GPIOD, clock_PIN)) { // Turn on LED GPIO_SetBits(GPIOD, LED_PIN); Delay_Ms(1000); // Keep LED on for 1 s // Turn off LED GPIO_ResetBits(GPIOD, LED_PIN);

     }
     Delay_Ms(1000);  

}

int main() { NVIC_PriorityGroupConfig(NVIC_PriorityGroup_1); // Configure the NVIC priority group SystemCoreClockUpdate(); // Update system core clock Delay_Init(); // Initialize delay function setup(); // Configure GPIO pins

     while (1) {
    loop();
     }

     return 0;
}

void NMI_Handler(void) {} void HardFault_Handler(void) { while (1) { } }

****************** END *******************

# Testing & verification

1. Using Vivado simulator synthesize and implement the clock divider circuit
2. Generate the bitstream
3. Dump the bitstream to VSDminquadron board and verify the output
4. Verify the output for different conditions
   
![circuit connection](https://github.com/user-attachments/assets/999dd6cf-611f-4d4a-83bf-449710787ace)








