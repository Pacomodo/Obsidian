##### 1. Write the definitions of the following terms.

###### (a) Moore’s Law
It means that the number of transistors will double every 2 years.
###### (b) Abstraction
It means that hiding details when they are not important.
###### (c) Discipline
Discipline is the act of intentionally restricting design choices. By discipline, we can work more productively at a higher level of abstraction. For example, we view voltages are discrete instead of continuous. By doing so, it is simpler to design than analog circuits.
##### 2. What is the largest (most positive) $16$-bit binary number that can be represented with (write in a decimal number and justify your answers) 
###### (a) unsigned numbers?
$2^{16} - 1 = 65535_{10}$
Note that the range of $N$-bit unsigned binary number is $[0,2^{N}-1]$.
###### (b) two’s complement numbers?
$2^{15}-1 = 32767_{10}$
Note that the range of $N$-bit two's complement number is $[-2^{N-1},2^{N-1}-1]$.
###### (c) sign/magnitude numbers?
$2^{15}-1 = 32767_{10}$
Note that the range of $N$-bit sign/magnitude number is $[-(2^{N-1}-1),2^{N-1}-1]$.
##### 3. What is the smallest (most negative) $16$-bit binary number that can be represented with (write in a decimal number and justify your answers)
###### (a) unsigned numbers?
$0_{10}$
Note that the range of $N$-bit unsigned binary number is $[0,2^{N}-1]$.
###### (b) two’s complement numbers?
$-2^{15}=-32768_{10}$
Note that the range of $N$-bit two's complement number is $[-2^{N-1},2^{N-1}-1]$.
###### (c) sign/magnitude numbers?
$-(2^{15}-1) = -32767_{10}$
Note that the range of $N$-bit sign/magnitude number is $[-(2^{N-1}-1),2^{N-1}-1]$.
##### 4. Assuming you have $64$ GB of main memory in your computer, how many bits are required to represent the address of the main memory?
 Note that 1 address is map to the 1 byte of data. If we have 64GB of main memory, it is same as $64\text{GB} = 2^{6}\cdot 2^{30}\text{Byte}=2^{36}\text{Byte}$. So, we need $36$ bits to represent the address of the main memory.
##### 5. Convert the following two’s complement binary numbers to decimal.
###### (a) 1111 
$1111 \xrightarrow{\text{take 2's complement}} 0001_{2} = 1_{10}$
###### (b) 101011
$101011\to 010101_{2}=21_{10}$
###### (c) 01000110
$01000110 \to 10111010_{2} = 2+8+16+32+128 = 186_{10}$
###### (d) 10100101
$10100101 \to 01011011_{2} = 1+2+8+16+64 = 91_{10}$
##### 6. Convert the following decimal numbers to 8-bit two’s complement numbers or indicate that the decimal number would overflow the range.
Note that the range of $N$-bit two's complement number is $[-2^{N-1},2^{N-1}-1]$.
So, the range of $8$-bit two's complement number is $[-2^{7},2^{7}-1]=[-128,127]$.
###### (a) 22
$22_{10} = 16+4+2 = 0001 \ 0110_{2}$ 
###### (b) -49
$49_{10} = 32 + 16 + 1 = 0011 \ 0001_{2} \xrightarrow{\text{taking 2's complement}} 1100 \ 1111$
###### (c) 128
The decimal number will overflow the range.
###### (d) -140
The decimal number will overflow the range.
###### (e) 127
$0111\ 1111_{2}$
##### 7. Convert the following decimal numbers to 6-bit two’s complement binary numbers and add them. Indicate whether the sum overflows a 6-bit result. Please justify your answer (i.e., show your work).
Note that the range of $N$-bit two's complement binary number is $[-2^{N-1},2^{N-1}-1]$.
So, the range of $6$-bit two's complement binary number is $[-2^{5},2^{5}-1]=[-32,31]$.
###### (a) 16 + 8
$16 = 010 \ 000_{2}$
$8 = 001 \ 000_{2}$
$$
\begin{align}
&010 \ 000 \\
+\ &001 \ 000 \\
= \ &011 \ 000_{2} \\
= \ &24_{10}
\end{align}
$$
###### (b) 30 + 31
The sum will overflows $6$-bit result.
###### (c) -9 + 19
$9 = 8+1 = 001 \ 001_{2} \xrightarrow{\text{taking 2's complement}} 110 \ 111$
$19 = 16+2+1 = 010 \ 011_{2}$
$$
\begin{align}
&110 \ 111 \\
+\ &010 \ 011 \\
=\ &001 \ 010 \\
=\ &10_{10}
\end{align}
$$
###### (d) 6 + (-32)
$6 = 4+2 = 000 \ 110_{2}$
$32 = 100 \ 000_{2} \xrightarrow{\text{taking 2's complement}} 100 \ 000_{2}$
$$
\begin{align}
&000 \ 110 \\
+\ &100 \ 000 \\
=\ &100 \ 110 \\
=\ & -2^{5}+2^{2}+2^{1} \\
=\ & -26_{10}
\end{align}
$$
###### (e) -15 + (-9)
$15 = 8+4+2+1 = 001 \ 111_{2} \xrightarrow{\text{taking 2's complement}} 110 \ 001$
$9 = 8+1 = 001 \ 001_{2} \xrightarrow{\text{taking 2's complement}}110\ 111$
$$
\begin{align}
&110 \ 001 \\
+\ &110 \ 111 \\
=\ &101 \ 000 \\
=\ & -2^{5}+2^{3} \\
=\ & -24_{10}
\end{align}
$$
###### (f) -24 + (-31) 
The sum will overflows $6$-bit result.
##### 8. In a binary coded decimal (BCD) system, 4 bits are used to represent a decimal digit from 0 to 9. For instance, 3710 is written as $0011 \ 0111_{\text{BCD}}$.
###### (a) Write 2510 in BCD.
$2510 = 0010 \ 0101 \ 0001 \ 0000_{\text{BCD}}$
###### (b) Convert $1001 \ 0101 \ 0001_{\text{BCD}}$ to decimal.
$1001 \ 0101 \ 0001_{\text{BCD}} = 951_{10}$
###### (c) Convert $1001 \ 0101 \ 0001_{\text{BCD}}$ to binary. 
$1001 \ 0101 \ 0001_{\text{BCD}} = 951_{10} = 11 \ 1011 \ 0111_{2}$
##### 9. A majority gate produces a TRUE output if and only if more than half of its inputs are TRUE. Complete  a truth table for the three-input (A, B, and C) majority gate that produces output Y.

|  A  |  B  |  C  |  Y  |
| :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  0  |
|  0  |  0  |  1  |  0  |
|  0  |  1  |  0  |  0  |
|  0  |  1  |  1  |  1  |
|  1  |  0  |  0  |  0  |
|  1  |  0  |  1  |  1  |
|  1  |  1  |  0  |  1  |
|  1  |  1  |  1  |  1  |

##### 10. A three-input AND-OR (AO) gate shown in the below figure produces a TRUE output if both A and B are TRUE or if C is TRUE. Complete a truth table for the gate.
![[Pasted image 20240409123207.png|center]]

|  A  |  B  |  C  |  Y  |
| :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  0  |
|  0  |  0  |  1  |  1  |
|  0  |  1  |  0  |  0  |
|  0  |  1  |  1  |  1  |
|  1  |  0  |  0  |  0  |
|  1  |  0  |  1  |  1  |
|  1  |  1  |  0  |  1  |
|  1  |  1  |  1  |  1  |

##### 11. Write a truth table for the function performed by the gate in the below figure. The truth table should have two inputs, A and B. Figure out the logic gate of this function? 

![[Pasted image 20240409141548.png|center]]
Let's number the P-MOS transistors in the figure above from left to right and top to bottom: 1, 2, 3, 4. Similarly, number the N-MOS transistors: 5, 6, 7, 8.
If $A$ and $B$ flows nothing(0 and 0), then 2 and 4 is off, so $Y$ flows nothing.
If $A$ is $1$ and $B$ flows nothing(0), then, 1 and 4 is off, 5 and 8 is off, so, current flows to $Y$.
If $A$ is 0 and $B$ is 1, then, 2 and 3 is off, 6 and 7 is off, so, current flows to $Y$.
If $A$ and $B$ are both 1, then, 1 and 3 is off, so, $Y$ flows nothing.

|  A  |  B  |  Y  |
| :-: | :-: | :-: |
|  0  |  0  |  0  |
|  0  |  1  |  1  |
|  1  |  0  |  1  |
|  1  |  1  |  0  |
This logic gate behaves like XOR gate.
##### 12. Write a truth table for the function performed by the gate in the below figure. The truth table should have three inputs, A, B, and C.

![[Pasted image 20240409143659.png|center]]
If $A,B,C$ are all 0, then, all P-MOS transistors are on, N-MOS transistors are off, so, current flows to $Y$. 
If $C$ is 1, then, P-MOS transistor connected to input $C$ is off, so, current does not flow to $Y$.
If $A$ and $B$ are both 1, then, P-MOS transistors connected to input $A$ and $B$ are off, so, current does not flow to $Y$.
If $A$ is 0, $B$ is 1 and $C$ is 0, then, N-MOS transistors connected to input $A$ and $C$ are off, P-MOS transistors to input $A$ and $C$ are on, so, current flows to $Y$.
If $A$ is 1, $B$ is 0 and $C$ is 0, then, N-MOS transistors connected to input $B$ and $C$ are off, P-MOS transistors to input $B$ and $C$ are on, so, current flows to $Y$.

|  A  |  B  |  C  |  Y  |
| :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  1  |
|  0  |  0  |  1  |  0  |
|  0  |  1  |  0  |  1  |
|  0  |  1  |  1  |  0  |
|  1  |  0  |  0  |  1  |
|  1  |  0  |  1  |  0  |
|  1  |  1  |  0  |  0  |
|  1  |  1  |  1  |  0  |
