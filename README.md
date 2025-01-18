
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

> Opcode (7 bits)

Identifies the broad category of the instruction (e.g., arithmetic, logical, shift). The opcode determines the type of operation and the instruction format (e.g., R- type, I-type, S-type).

Placement: Bits [6:0].

Examples: 0110011: R-type operations (add, sub, and, or, etc.).

> rd (Destination Register, 5 bits)

Specify the register where the result of the operation will be stored.

Placement: Bits [11:7].

The register index ranges from 0 to 31, corresponding to the 32 general-purpose registers in RISC-V (e.g., x0 to x31). Writing to x0 is effectively a NOP (writes are ignored since x0 is hardwired to 0).

Example: If rd = 01010, it means the result is stored in register x10.

> rd (Destination Register, 5 bits)

Specifies the specific operation to be performed within the instruction category defined by opcode.

Placement: Bits [14:12]. funct3 works in combination with funct7 to differentiate between similar operations. Common values: 000: Add or subtract (depending on funct7). 111: AND operation. 110: OR operation.

Examples: For an ADD instruction: funct3 = 000. For an AND instruction: funct3 = 111.

 > rs1 (Source Register 1, 5 bits)

Specifies the first source register containing one of the operands.

Placement: Bits [19:15].

The register index ranges from 0 to 31, like rd. It holds the value used in computation or logical operation.

Example: If rs1 = 00001, it means the first operand is in register x1.

 >  rs2 (Source Register 2, 5 bits)

Specifies the second source register containing the second operand.

Placement: Bits [24:20].

Like rs1, the register index ranges from 0 to 31. It provides the second value used in computations.

Example: If rs2 = 00010, it means the second operand is in register x2.

 >  funct7 (Function Code, 7 bits)

Provides additional specificity to distinguish between operations that share the same opcode and funct3.

Placement: Bits [31:25].

This field is essential for certain instructions with similar opcode and funct3 but different behaviors. Common values: 0000000: Standard operation (e.g., add). 0100000: Alternative operation (e.g., sub).

Examples: For ADD: funct7 = 0000000. For SUB: funct7 = 0100000.

 













