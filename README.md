
# GAT-RISC-V-ROADSHOW


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

   . Opcode (7 bits)

Identifies the broad category of the instruction (e.g., arithmetic, logical, shift). The opcode determines the type of operation and the instruction format (e.g., R- type, I-type, S-type).

Placement: Bits [6:0].

Examples: 0110011: R-type operations (add, sub, and, or, etc.).

  . rd (Destination Register, 5 bits)

Specify the register where the result of the operation will be stored.

Placement: Bits [11:7].

The register index ranges from 0 to 31, corresponding to the 32 general-purpose registers in RISC-V (e.g., x0 to x31). Writing to x0 is effectively a NOP (writes are ignored since x0 is hardwired to 0).

Example: If rd = 01010, it means the result is stored in register x10.

  . rd (Destination Register, 5 bits)

Specifies the specific operation to be performed within the instruction category defined by opcode.

Placement: Bits [14:12]. funct3 works in combination with funct7 to differentiate between similar operations. Common values: 000: Add or subtract (depending on funct7). 111: AND operation. 110: OR operation.

Examples: For an ADD instruction: funct3 = 000. For an AND instruction: funct3 = 111.

  . rs1 (Source Register 1, 5 bits)

Specifies the first source register containing one of the operands.

Placement: Bits [19:15].

The register index ranges from 0 to 31, like rd. It holds the value used in computation or logical operation.

Example: If rs1 = 00001, it means the first operand is in register x1.

 . rs2 (Source Register 2, 5 bits)

Specifies the second source register containing the second operand.

Placement: Bits [24:20].

Like rs1, the register index ranges from 0 to 31. It provides the second value used in computations.

Example: If rs2 = 00010, it means the second operand is in register x2.

 . funct7 (Function Code, 7 bits)

Provides additional specificity to distinguish between operations that share the same opcode and funct3.

Placement: Bits [31:25].

This field is essential for certain instructions with similar opcode and funct3 but different behaviors. Common values: 0000000: Standard operation (e.g., add). 0100000: Alternative operation (e.g., sub).

Examples: For ADD: funct7 = 0000000. For SUB: funct7 = 0100000.

 
# 2.The I-Type(Immediate-Type)

The I-type (Immediate-type) instruction format in RISC-V is used for instructions that operate on one register operand and an immediate value. These instructions are common for operations such as memory access, arithmetic with constants, or conditional jumps. The I-type format has the following fields:

  . opcode (7 bits): Identifies the type of instruction (e.g., arithmetic, memory access, etc.).

Placement: Bits [6:0].

Common opcodes for I-type: 0000011: Load instructions (e.g., lw for load word). 0010011: Arithmetic instructions with an immediate (e.g., addi).

 . rd (Destination Register, 5 bits): Specifies the destination register where the result of the operation will be stored. Placement: Bits [11:7]. Holds the result of the operation (e.g., the value loaded from memory or the result of arithmetic with the immediate). Example: If rd = 00010, the result is written to register x2.

 . funct3 (Function Code, 3 bits): Specifies the specific operation within the instruction type.

Placement: Bits [14:12].

Differentiates between operations like addi, slti, or load instructions like lb (load byte), lw (load word).

Examples: 000: Add immediate (addi). 010: Set less than immediate (slti). 100: XOR immediate (xori).

  . rs1 (Source Register 1, 5 bits): Specifies the register providing the first operand.

Placement: Bits [19:15].

The value in this register is combined with the immediate value (imm) in the specified operation.

Example: If rs1 = 00001, it means the value in register x1 is used as the operand.

  . imm (Immediate Value, 12 bits): Provides a constant value or offset for the instruction.

Placement: Bits [31:20].

Signed 12-bit value (using two's complement). Can represent values in the range of -2048 to 2047. Zero-extended or sign-extended as needed based on the operation. Used for: Arithmetic operations (e.g., addi adds rs1 and imm). Load instructions (e.g., memory address is rs1 + I'm).

Examples: For addi x3, x2, 10: imm = 10 (decimal). For lw x5, 100(x1): imm = 100 (offset).

# 3. The S-type (Store-type)

The S-type (Store-type) instruction format in RISC-V is designed for instructions that store data from a register in memory. It uses a combination of a base address from one register and an immediate offset to calculate the effective memory address.

The S-type format has the following fields:

  . opcode (7 bits): Identifies the type of instruction (store in this case).

Placement: Bits [6:0].

The common opcode for S-type instructions: 0100011: Store instructions (e.g., sw, sh, sb).

Example: For a store word (sw) instruction: opcode = 0100011.

  . imm (Immediate Value, 12 bits total): Specifies the offset to be added to the base address in rs1 to calculate the effective memory address.

Placement: Upper 7 bits (imm[11:5]): Bits [31:25]. Lower 5 bits (imm[4:0]): Bits [11:7].

Immediate is a signed 12-bit value (using two's complement).Can represent offsets from -2048 to 2047. The two parts (imm[11:5] and imm[4:0]) are combined during instruction decoding to form the complete immediate.

Example: If imm[11:5] = 0000001 and imm[4:0] = 01010, the full immediate is 000000101010 (42 in decimal).

  . rs2 (Source Register 2, 5 bits): Specifies the register holding the data to be stored in memory.

Placement: Bits [24:20].

The contents of this register are written to the memory address calculated from rs1 + imm.

Example: If rs2 = 00010, the data to be stored comes from register x2.

  . rs1 (Source Register 1, 5 bits): Specify the register holding the base address for memory access.

Placement: Bits [19:15].

The effective memory address is calculated as rs1 + imm.

Example: If rs1 = 00001, the base address comes from register x1.

  . funct3 (Function Code, 3 bits): Specifies the type of data to be stored (e.g., byte, half-word, word).

Placement: Bits [14:12].

Determines the size of the data being stored. Common values: 000: Store byte (sb). 001: Store half-word (sh). 010: Store word (sw).

Example: For a store word instruction: funct3 = 010.

# 4. The U-type instruction 

The U-type instruction format in the RISC-V architecture is used primarily for instructions that involve immediate values, typically for forming larger constants or calculating addresses. The U-type format is part of the 32-bit RISC-V instruction set. The U-type instruction has the following 32-bit structure:

  . Immediate (31–12):

This is a 20-bit field that provides the upper 20 bits of a constant or address. The value is sign-extended when needed. The lower 12 bits are typically assumed to be zeros.

  . Destination Register (rd) (11–7): Specifies the register where the result of the instruction will be stored.

  . Opcode (6–0): Identifies the specific instruction. For U-type, common opcodes are: LUI (Load Upper Immediate): Opcode 0110111. AUIPC (Add Upper Immediate to PC): Opcode 0010111.

# 5. The B-type (Branch-type)

The B-type(Branch-type)instruction format in RISC-V is designed for conditional branch instructions that control the flow of execution based on a comparison
between two registers. These instructions are typically used to implement if-else conditions, loops, and other control flow operations. The B-type format has the following fields:

  . opcode (7 bits): Identifies the type of instruction (branch in this case).

Placement: Bits [6:0].

The opcode for B-type instructions is 1100011. This indicates that the instruction is related to branching.

Example: For a branch instruction: opcode = 1100011.

  . imm (Immediate Value, 13 bits): Provides the offset that is added to the program counter (PC) when the branch condition is met. This offset is calculated relative to the next instruction (PC + 4).

Placement: imm[12]: The most significant bit (bit 12). imm[10:5]: Bits [10:5] for the middle 6 bits. imm[4:1]: Bits [4:1] for the least significant 4 bits. imm[11]: The second most significant bit (bit 11).

The immediate value is signed (using two's complement) and is used to calculate the address of the target instruction. The immediate is shifted left by 1 bit during instruction decoding to account for word-aligned addresses.

Example: If imm[12] = 0, imm[10:5] = 000100, imm[4:1] = 0101, and imm[11] = 1, the complete immediate would be 000100010101 (in binary), which is 0x115 (277 in decimal).

  . rs2 (Source Register 2, 5 bits): Specifies the second register that is compared to rs1 for the branch decision.

Placement: Bits [24:20].

The value in rs2 is compared with the value in rs1. This field is used in the comparison operation for the branch (e.g., beq, bne).

Example: If rs2 = 00010, the second operand is x2.

  . rs1 (Source Register 1, 5 bits): Specifies the first register that is compared to rs2.

Placement: Bits [19:15].

The value in rs1 is compared with the value in rs2. For a beq (branch if equal) instruction, if the values in rs1 and rs2 are equal, the branch is taken.

Example: If rs1 = 00001, the first operand is x1.

  . funct3 (Function Code, 3 bits): Specify the type of comparison (e.g., equal, not equal, greater than, etc.).

Placement: Bits [14:12].

The comparison determines whether the branch will be taken. Common values: 000: Branch if equal (beq). 001: Branch if not equal (bne). 100: Branch if less than (blt). 101: Branch if greater than or equal (bge). 110: Branch if unsigned less than (bltu). 111: Branch if unsigned greater than or equal (bgeu).\n Examples:

beq (branch if equal): funct3 = 000. bne (branch if not equal): funct3 = 001.

# 6.The J-Type(Jump-Type)

The J-type (Jump-type) The J-type (Jump-type) instruction format in RISC-V is designed for unconditional jump operations. These instructions allow the program to change its execution flow by jumping to an address specified by a 12-bit signed immediate value. The immediate value is used to calculate the target address relative to the current Program Counter (PC).

Placement: Bits [19:15].

The J-type format has the following fields:

  . opcode (7 bits): Identifies the type of instruction. In J-type, the opcode specifies that the instruction is a jump.

Placement: Bits [6:0].

The opcode for J-type instructions is always 1101111 (which indicates the jump instruction category).

Example: For a jump instruction (jal or jalr), opcode = 1101111.

  . imm (Immediate Value, 21 bits total): Purpose: Specifies the offset to be added to the current Program Counter (PC) to calculate the target address.

Placement: imm[20]: Most significant bit of the immediate value (bit 20). imm[10:1]: Middle 10 bits of the immediate value. imm[11]: Second most significant bit (bit 11). imm[19:12]: Lower 8 bits of the immediate value.

The immediate value is signed and used to calculate the target address relative to the current instruction. The immediate value is shifted left by 1 bit to account for the word-aligned address (because instructions are 4 bytes in RISC-V). This offset allows the jump to be within a ±1 MiB range (a total of 2^20 bytes, or 2^18 words).

Example: If imm[20] = 0, imm[10:1] = 0101010101, imm[11] = 1, and imm[19:12] = 10101010, the full immediate value would be 0101010101101010101 (in binary), which is 0x55555 (349525 in decimal).

  . rs1 (5 bits): Purpose: This field is not used in J-type instructions and is always 0. It is reserved for compatibility with other instruction formats.


# 32-bit instructions code

![RISC-V 2](https://github.com/user-attachments/assets/3c045f64-9889-43ea-8f53-f8bcc866483a)








