|         Category         |             Instruction              |       Example        |           Meaning            |                          Comments                          |
| :----------------------: | :----------------------------------: | :------------------: | :--------------------------: | :--------------------------------------------------------: |
|      **Arithmetic**      |                 Add                  |   `add x5, x6, x7`   |        `x5 = x6 + x7`        |                Three register operands; add                |
|                          |               Subtract               |   `sub x5, x6, x7`   |        `x5 = x6 - x7`        |             Three register operands; subtract              |
|                          |            Add immediate             |  `addi x5, x6, 20`   |        `x5 = x6 + 20`        |                   Used to add constants                    |
|    **Data transfer**     |              Load word               |   `lw x5, 40(x6)`    |    `x5 = Memory[x6 + 40]`    |                Word from memory to register                |
|                          |         Load word, unsigned          |   `lwu x5, 40(x6)`   |    `x5 = Memory[x6 + 40]`    |           Unsigned word from memory to register            |
|                          |              Store word              |   `sw x5, 40(x6)`    |    `Memory[x6 + 40] = x5`    |                Word from register to memory                |
|                          |            Load halfword             |   `lh x5, 40(x6)`    |    `x5 = Memory[x6 + 40]`    |              Halfword from memory to register              |
|                          |       Load halfword, unsigned        |   `lhu x5, 40(x6)`   |    `x5 = Memory[x6 + 40]`    |         Unsigned halfword from memory to register          |
|                          |            Store halfword            |   `sh x5, 40(x6)`    |    `Memory[x6 + 40] = x5`    |              Halfword from register to memory              |
|                          |              Load byte               |   `lb x5, 40(x6)`    |    `x5 = Memory[x6 + 40]`    |                Byte from memory to register                |
|                          |         Load byte, unsigned          |   `lbu x5, 40(x6)`   |    `x5 = Memory[x6 + 40]`    |           Byte unsigned from memory to register            |
|                          |              Store byte              |   `sb x5, 40(x6)`    |    `Memory[x6 + 40] = x5`    |                Byte from register to memory                |
|                          |            Load reserved             |    `l.r.d x5, x6`    |      `x5 = Memory[x6]`       |               Load; 1st half of atomic swap                |
|                          |          Store conditional           |   `sc.d x5, 0(x6)`   |      `Memory[x6] = x5`       |               Store; 2nd half of atomic swap               |
|                          |         Load upper immediate         | `lui x5, 0x12345000` |      `x5 = 0x12345000`       |         Loads 20-bit constant shifted left 12 bits         |
|       **Logical**        |                 And                  |   `and x5, x6, x7`   |        `x5 = x6 & x7`        |            Three reg. operands; bit-by-bit AND             |
|                          |             Inclusive or             |   `or x5, x6, x7`    |       `x5 = x6 \| x7`        |             Three reg. operands; bit-by-bit OR             |
|                          |             Exclusive or             |   `xor x5, x6, x9`   |        `x5 = x6 ^ x9`        |            Three reg. operands; bit-by-bit XOR             |
|                          |            And immediate             |  `andi x5, x6, 20`   |        `x5 = x6 & 20`        |             Bit-by-bit AND reg. with constant              |
|                          |        Inclusive or immediate        |   `ori x5, x6, 20`   |       `x5 = x6 \| 20`        |              Bit-by-bit OR reg. with constant              |
|                          |        Exclusive or immediate        |  `xori x5, x6, 20`   |        `x5 = x6 ^ 20`        |             Bit-by-bit XOR reg. with constant              |
|        **Shift**         |          Shift left logical          |   `sll x5, x6, x7`   |       `x5 = x6 << x7`        |                   Shift left by register                   |
|                          |         Shift right logical          |   `srl x5, x6, x7`   |       `x5 = x6 >> x7`        |                  Shift right by register                   |
|                          |        Shift right arithmetic        |   `sra x5, x6, x7`   |       `x5 = x6 >> x7`        |             Arithmetic shift right by register             |
|                          |     Shift left logical immediate     |   `slli x5, x6, 3`   |        `x5 = x6 << 3`        |                  Shift left by immediate                   |
|                          |    Shift right logical immediate     |   `srli x5, x6, 3`   |        `x5 = x6 >> 3`        |                  Shift right by immediate                  |
|                          |   Shift right arithmetic immediate   |   `srai x5, x6, 3`   |        `x5 = x6 >> 3`        |            Arithmetic shift right by immediate             |
|  **Conditional branch**  |           Branch if equal            |  `beq x5, x6, 100`   | `if (x5 == x6) go to PC+100` |           PC-relative branch if registers equal            |
|                          |         Branch if not equal          |  `bne x5, x6, 100`   | `if (x5 != x6) go to PC+100` |         PC-relative branch if registers not equal          |
|                          |         Branch if less than          |  `blt x5, x6, 100`   | `if (x5 < x6) go to PC+100`  |            PC-relative branch if registers less            |
|                          |      Branch if greater or equal      |  `bge x5, x6, 100`   | `if (x5 >= x6) go to PC+100` |      PC-relative branch if registers greater or equal      |
|                          |       Branch if less, unsigned       |  `bltu x5, x6, 100`  | `if (x5 < x6) go to PC+100`  |       PC-relative branch if registers less, unsigned       |
|                          | Branch if greater or equal, unsigned |  `bgeu x5, x6, 100`  | `if (x5 >= x6) go to PC+100` | PC-relative branch if registers greater or equal, unsigned |
| **Unconditional branch** |            Jump and link             |    `jal x1, 100`     |  `x1 = PC+4; go to PC+100`   |                 PC-relative procedure call                 |
|                          |        Jump and link register        |  `jalr x1, 100(x5)`  |  `x1 = PC+4; go to x5+100`   |              Procedure return; indirect call               |

###### 1. For the RISC-V assembly instructions below, what is the corresponding C statement? Assume that the variables `f`, `g`, `h`, `i`, and `j` are assigned to registers `x5`, `x6`, `x7`, `x28`, and `x29`, respectively. Assume that the base address of the array `A` and `B` are in registers `x10` and `x11`, respectively. The size of a single element of the array `A` and `B` is 4 bytes.
```assembly
 slli x30, x5, 2 // x30 = f*4 
 add x30, x10, x30 // x30 = &A[f] 
 slli x31, x6, 2 // x31 = g*4 
 add x31, x11, x31 // x31 = &B[g] 
 lw x5, 8(x30) 
 addi x12, x30, 16 
 lw x30, 0(x12) 
 add x30, x30, x5 
 slli  x30, x30, 3 
 sw x30, -8(x31)
 ```
Sol)
```assembly
 slli x30, x5, 2 
 add x30, x10, x30 
 slli x31, x6, 2 
 add x31, x11, x31 
 lw x5, 8(x30)
 addi x12, x30, 16 
 lw x30, 0(x12) 
 add x30, x30, x5 
 slli  x30, x30, 3 
 sw x30, -8(x31) 
 ```
 
 ```C
 B[g-2] = (A[f+2] + A[f+4]) * 8;
 ```

###### 2. Translate the following RISC-V code to C. Assume that the variables `f`, `g`, `h`, `i`, and `j` are assigned to registers `x5`, `x6`, `x7`, `x28`, and `x29`, respectively. Assume that the base address of the array `A` and `B` are in registers `x10` and `x11`, respectively. The size of a single element of the array `A` and `B` is 4 bytes. (Hint: `&x` represents the address of a variable ‘`x`’ in C).
```Assembly
addi x30, x10, 16 
addi x31, x10, 8 
sw x31, 0(x30) 
lw x30, 0(x30) 
add x30, x30, x31 
addi x6, x30, -12
```

Sol)
To translate the given RISC-V assembly instructions into a corresponding C statement, let's analyze each instruction step by step. We'll assume that `A` is an array of pointers (`int*`) to accommodate storing addresses within the array.
```assembly
addi x30, x10, 16    // x30 = x10 + 16
addi x31, x10, 8     // x31 = x10 + 8
```
`x30` now holds the address `&A[4]` (since each `A` element is 4 bytes: `16 bytes / 4 bytes per element = 4`). `x31` holds the address `&A[2]`.
```assembly
sw x31, 0(x30)       // Memory[x30] = x31
```
This stores the value of `x31` (which is `&A[2]`) into the memory location pointed to by `x30` (which is `&A[4]`). In C, `A[4] = &A[2];`
```assembly
lw x30, 0(x30)       // x30 = Memory[x30]
```
Now, `x30` contains the value stored at `A[4]`, which is `&A[2]`.
```assembly
add x30, x30, x31    // x30 = x30 + x31
```
This adds the addresses `&A[2] + &A[2]`, resulting in `x30 = 2 * &A[2]`.
```assembly
addi x6, x30, -12    // x6 (g) = x30 - 12
```
Subtracting 12 bytes from `2 * &A[2]`.
```c
#include <stdint.h>
A[4] = (intptr_t)&A[2];
g = A[4] + (intptr_t)&A[2] - 12;
```
We use `intptr_t` (from `<stdint.h>`) to safely convert pointers to integer types for arithmetic operations.
###### 3. Answer for the following questions.
(a) Translate the following C code to RISC-V assembly code straightforwardly. Assume that the 
variables `f` and `i` are assigned to registers `x5` and `x6`, respectively. Assume that the base address of the array `A` and `B` are in registers `x10` and `x11`, respectively. The size of a single element of the array `A` and `B` is 4 bytes. (Use `x28`, `x29`, `x30`, and `x31` as registers for temporary data. You should minimize the lines of your code.)
```C
for (i = 15; i >= 0; i--) { 
    f = A[i]; 
    A[i] = B[i]; 
    B[i] = f; 
}
```

Sol)
```Assembly
    addi   x6, x0, 15        
Loop:
    slli   x28, x6, 2        
    add    x29, x10, x28    
    lw     x5, 0(x29)        
    add    x30, x11, x28    
    lw     x31, 0(x30)       
    sw     x31, 0(x29)       
    sw     x5, 0(x30)        
    addi   x6, x6, -1        
    bge    x6, x0, Loop     
```

(b) The above C code shown in Questions 3-(a) can be rewritten using pointers `pA` and `pB` as follows. Translate the following C code to RISC-V assembly code. Assume that the variables `f` and `i` are assigned to registers `x5` and `x6`, respectively. Assume that the base address of the array `A` and `B` are in registers `x10` and `x11`, respectively. The size of a single element of the array `A` and `B` is 4 bytes. (Use `x28`, `x29`, `x30`, and `x31` as registers for temporary data. You should minimize the lines of your code.)
```C
pB = &B[15]; 
for (pA = &A[15]; pA >= &A[0]; pA = pA - 1) { 
    f = *pA 
    *pA = *pB; 
    *pB = f; 
    pB = pB – 1; 
}
```

Sol)
```Assembly
    addi    x28, x10, 60      
    addi    x29, x11, 60      
Loop:
    lw     x5, 0(x28)        
    lw     x30, 0(x29)      
    sw     x30, 0(x28)       
    sw     x5, 0(x29)        
    addi   x28, x28, -4      
    addi   x29, x29, -4      
    bgeu   x28, x10, Loop    
```

(c) Assuming the CPI of every instruction is the same, compare the performance of the above two codes.

Sol)
Code from (a) executes 9 instructions per loop and code from (b) executes 7 instructions per loop. Initialization instructions in (a) and (b) are 1 and 2. The number of loops is 16.
So,
$$
\frac{t_{a}}{t_{b}} = \frac{16\cdot 9+1}{16\cdot 7 + 2} = \frac{145}{114}\approx 1.27
$$
Code (b) will perform 27% better then code (a).

###### 4. Consider the following RISC-V loop.
```Assembly
	 addi x5, x0, 0 
	 addi x6, x0, 200 
LOOP: blt x6, x0, DONE 
	 addi x6, x6, -1 
	 addi x5, x5, 5 
	 jal x0, LOOP 
DONE:
```
(a) What is the final value in register `x5`? Represent your answer in a hexadecimal format.
Sol)
`0x000003ED`
(b) For the loop above, write the equivalent C code. Assume that the registers `x5` and `x6` are integers `i` and `j`, respectively.
Sol)
```C
i = 0;
j = 200;
while (j >= 0) {
    j = j - 1;
    i = i + 5;
}
```

###### 5. The following RISC-V assembly code represents the recursive factorial function: f(n) = n!. In the following code `sp` means stack pointer (=`x2`) and `x1` is used for storing return address. A hexadecimal number preceding each assembly instruction means a program counter of the corresponding instruction.
```
0x0080 fact: addi sp, sp, -8 
0x0084       sw x1, 4(sp) 
0x0088       sw x10, 0(sp) 
0x008C       addi x5, x10, -1 
0x0090       bge x5, x0, L1 
0x0094       addi x10, x0, 1 
0x0098       addi sp, sp, 8 
0x009C       jalr x0, 0(x1) 
0x00A0 L1: addi x10, x10, -1 
0x00A4     jal x1, fact 
0x00A8     addi x6, x10, 0 
0x00AC     lw x10, 0(sp) 
0x00B0     lw x1, 4(sp) 
0x00B4     addi sp, sp, 8 
0x00B8     mul x10, x10, x6 
0x00BC     jalr x0, 0(x1) 
```
(a) Figure out basic blocks in the above assembly code. You should represent a basic block with a range of the program counters. For example, `BB1: 0x0080~0x0088`. How many basic blocks exist in the above code?

Sol)
Note that A basic block is a sequence of consecutive instructions with no branch targets except at the first instruction and no branch instructions except possibly at the last instruction.
So, There are 4 basic blocks in the code:
1. **BB1:** `0x0080` ~ `0x0090`
2. **BB2:** `0x0094` ~ `0x009C`
3. **BB3:** `0x00A0` ~ `0x00A4`
4. **BB4:** `0x00A8` ~ `0x00BC`

(b) Assuming the initial stack pointer is `0xFFF0`, describe how the stack pointer changes if n = 4.  Write your answer like the following example. (Hint: Consider how many times the function is called.) 
`0xFFF0 → 0xFFE0 → 0xFFE8 → 0xFFF0`

Sol)
`0xFFF0 → 0xFFE8 → 0xFFE0 → 0xFFD8 → 0xFFD0 → 0xFFC8 → 0xFFD0 → 0xFFD8 → 0xFFE0 → 0xFFE8 → 0xFFF0`

Initial Stack Pointer : `sp = 0xFFF0`
Function Calls and Stack Pointer Changes:

1. **Call with `n = 4`:** `sp = sp - 8 = 0xFFF0 - 8 = 0xFFE8`
2. **Call with `n = 3`:** `sp = sp - 8 = 0xFFE8 - 8 = 0xFFE0`
3. **Call with `n = 2`:** `sp = sp - 8 = 0xFFE0 - 8 = 0xFFD8`
4. **Call with `n = 1`:** `sp = sp - 8 = 0xFFD8 - 8 = 0xFFD0`
5. **Call with `n = 0`:** `sp = sp - 8 = 0xFFD0 - 8 = 0xFFC8`

Function Returns and Stack Pointer Restorations:

6. **Return from `n = 0`:** `sp = sp + 8 = 0xFFC8 + 8 = 0xFFD0`
7. **Return from `n = 1`:** `sp = sp + 8 = 0xFFD0 + 8 = 0xFFD8`
8. **Return from `n = 2`:** `sp = sp + 8 = 0xFFD8 + 8 = 0xFFE0`
9. **Return from `n = 3`:** `sp = sp + 8 = 0xFFE0 + 8 = 0xFFE8`
10. **Return from `n = 4`:** `sp = sp + 8 = 0xFFE8 + 8 = 0xFFF0`

(c) Let us assume that `ra` (=`x1`) contains `0x0040` when the function is first called by `jal`. Describe how the return address register (=`x1`) updated if n = 4. You need to write the value of the return address register whenever it is updated by instructions. (i.e. written by instructions). Please note the updating instruction using PC. Write your answer like the following example.
`0x0040 (initial) → 0x0080 (by inst of 0x0084) → 0x0080 (by inst of 0x0090) → 0x0040 (by intst of 0x0080).` 

Sol)
`0x0040 (initial) → 0x00A8 (by inst of 0x00A4) → 0x00A8 (by inst of 0x00A4) → 0x00A8 (by inst of 0x00A4) → 0x00A8 (by inst of 0x00A4) → 0x00A8 (by inst of 0x00B0) → 0x00A8 (by inst of 0x00B0) → 0x00A8 (by inst of 0x00B0) → 0x00A8 (by inst of 0x00B0) → 0x0040 (by inst of 0x00B0)`

(d) Rewrite the following instructions using immediate data. Namely you should figure out labels of the conditional branches. Use decimal numbers for immediate data. 

Sol)
`bge   x5, x0, L1  → bge x5, x0, 16` 
`jal   x1, fact  → jal x1, -36`
In `bge`:
Current PC: `0x0090`
Target Address (`L1`): `0x00A0`
Immediate Offset: `0x00A0 - 0x0090 = 0x10` (16 in decimal)
In `jal`:
Current PC: `0x00A4`
Target Address (fact): `0x0080`
Immediate Offset: `0x0080 - 0x00A4 = -0x24` (-36 in decimal)

###### 6. Assume for a given processor the CPI of arithmetic instructions is 1, the CPI of load/store instructions is 8, and the CPI of branch instructions is 3. Assume a program has following instructions breakdown: 800 million arithmetic instructions, 300 million load/store instructions, 200 million branch instructions.

(a) Suppose that new, more powerful arithmetic instructions are added to the instruction set. On average, through the use of these more powerful arithmetic instructions, we can reduce the number of arithmetic instructions needed to execute a program by 25%, while increasing the clock cycle time by only 5%. Is this a good design choice? Why?

Sol)
New arithmetic instruction count = $800\times 0.75 = 600$ millions.
New clock time = $1.05 \times \text{original clock time}$.
Total original cycles : 
$$
(800\times 1) + (300\times 8) + (200\times 3) \text{million} = 3800 \text{ million cycles}
$$
Total new cycles :
$$
(600 \times 1) + (300 \times 8) + (200 \times 3) \text{ million} = 3600 \text{ million cycles}
$$
New execution time :
$$
\text{Total new cycles}\times \text{New clock time} = 3600 \text{ million} \times 1.05 \times \text{original clock time}
$$
Original execution time:
$$
3800 \text{ million } \times \text{original clock time}
$$
Performance compare:
$$
\frac{3800}{3600\times 1.05} \approx 1.0053
$$
So, performance improved by approximately 0.53%, which is minimal. Increasing the clock cycle time by 5% negatively affects all instructions, not just arithmetic ones. In other words, increased clock cycle time affects the performance of load/store and branch instructions, which constitute a significant portion of the program (500 million instructions combined). Therefore, the proposed design choice is **not advantageous** due to minimal performance gains and increased clock cycle time.

(b) Suppose that we find a way to double the performance of arithmetic instructions. What is the overall speedup of our machine? What if we find a way to improve the performance of arithmetic instructions by 10 times?

Sol)
Case 1. Double the performance of arithmetic instructions.
New total cycles :
$$
\text{New total cycles} = (800 \times 0.5 + 300\times 8 + 200 \times 3) \text{ million cycles} = 3400  \text{ million cycles}
$$
Speed up :
$$
\frac{3800}{3400} \approx 1.12
$$
So, performance improved by 12% approximately.
Case 2. Performance of arithmetic instruction improved by 10 times.
New total cycles :
$$
\text{New total cycles} = (800 \times 0.1 + 300\times 8 + 200 \times 3) \text{ million cycles} = 3080  \text{ million cycles}
$$
Speed up:
$$
\frac{3800}{3080} \approx 1.23
$$
So, performance improved by 23% approximately.
###### 7. Let us assume you are to translate the following C code to RISC-V assembly code. Assume that the values of `a`, `b`, `i`, and `j` are in registers `x5`, `x6`, `x7`, and `x29`, respectively. Also, assume that register `x10` holds the base address of the array `D`. You can use `x30` and `x31` as temporary registers. The size of a single element of array `D` is 4 bytes.
```C
for (i=0; i < a; i++)
	for (j=0; j < b; j+=2) 
		D[2*j] = i + j;
```
Complete the following RISC-V assembly code.
```Assembly
	 addi x7, x0, 0 
LOOPI: bge 
	 addi 
	 addi x29, x0, 0 
LOOPJ: bge 
	 add 
	 sw 
	 addi 
	 addi 
	 jal 
ENDJ: addi 
	 jal 
ENDI:
```

Sol)
```Assembly
     addi x7, x0, 0                
LOOPI: bge x7, x5, ENDI            
       addi x31, x10, 0            
       addi x29, x0, 0            
LOOPJ: bge x29, x6, ENDJ           
       add x30, x7, x29            
       sw x30, 0(x31)            
       addi x31, x31, 16            
       addi x29, x29, 2            
       jal x0, LOOPJ              
ENDJ:  addi x7, x7, 1             
       jal x0, LOOPI          
ENDI: 
```
