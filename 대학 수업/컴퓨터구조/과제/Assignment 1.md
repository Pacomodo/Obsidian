##### 1. Write the definitions of the following terminologies. 
###### (a) Moore’s Law
It is observation that the number of transistor in IC will doubles about every 2 years.
###### (b) Dennard Scaling
It is theoretical principle about improving performance of IC without increasing power consumption.
$$
P_{dyn} = \alpha CV_{dd}^{2}f
$$
$C$ and $V_{dd}$ scale 1/$S$, where $S$ is transistor size. $f$ scales $S$, hence, $P_{dyn}$ scales $\frac{1}{S^{2}}$. The number of transistor in unit area grows $S^{2}$.
Therefore, power density stays constant, which means power consumption for same area stays constant.
However, it ends at very small transistor size, which preventing frequency scaling without increasing power consumption.

###### (c) Abstraction 
It means that hiding details when they are not important.
##### 2. Discuss why commodity CPU venders (such as Intel and AMD) do not manufacture single-core processors running with a very high clock frequency. Justify your answer.

By the end of dennard scaling, frequency scaling without power consumption is ended. As power increases, the more heats on processor are generated, which leads to throttling or damage to processor. Also, as frequency increases, performance are not linearly increasing, due to factors like memory latency and instruction pipeline delays. The processor may spend more time waiting for data from memory, which negating the benefits of higher clock speeds. Also, high frequency often leads to timing issues and potential errors. Therefore, making high clock frequency processor is expensive, which is cost-effectiveness. These many reasons leads to multicore-processor.
##### 3. Describe the steps that transform a program written in high-level language such as C into a representation that is **directly** executed by a computer processor.

Program written in high-level language translated into assembly language, which is textual representation of instructions, by language compiler. Assemply language translated into machine code that can be executed directly by a computer processor, by assembler.
##### 4. Computer $A$ can execute a C program 20 times in one second and Computer $B$ can execute the same C program 40 times in one second. If the MIPS (million instructions per second) rate of Computer $A$ is $\text{MIPS}_{A}$ and MIPS rate of Computer $B$ is $\text{MIPS}_{B}$, then an engineer concludes that $\text{MIPS}_B = \text{MIPS}_A \times 2$. Under what conditions is this calculation correct?

Computer $A$ and computer $B$ must have same instructions count per program.
Because MIPS defined as 
$$
\text{MIPS} = \frac{\text{Instruction count}}{\text{Execution time}\times 10^{6}}
$$

##### 5. Student Y stated that the performance of the ARM processor using 4 GHz clock exhibits higher performance than the x86 Pentium processor that runs with 2.5 GHz clock. Explain why the statement by Student Y is not always true. Please take a counter example in your answer.

Because Clock frequency alone, does not determine a processor's performance.
Performance is influenced by many factors, such as, instruction count, cycles per instruction, instruction set architecture(ISA), compilers for a program, etc.
Suppose a program $P$ executed on both processors.
ARM Processor (4 GHz) has instruction counts $1.5\times 10^6$ and average CPI 3.
x86 Pentium Processor (2.5 GHz) has $1\times 10^{6}$ and average CPI 1.5.
So, total cycles of ARM is $4.5\times 10^{6}$ and total cycles of Pentium is $1.5\times 10^{6}$.
Total execution time is
$$
\begin{align}
T_{\text{ARM}} = \frac{4.5\times10^{6}}{4\times 10^{9}} = 1.125 \times 10^{-3}(s) \\
T_{\text{Pentium}} = \frac{1.5\times10^{6}}{2.5\times 10^{9}} = 0.6 \times 10^{-3}(s)
\end{align}
$$
It means when this situation, Pentium processor is 1.875 times faster then ARM.
##### 6. Consider three different processors $P_{1}$, $P_{2}$, and $P_{3}$ executing the same instruction set. $P_{1}$ has 3.0GHz clock rate and a CPI of 1.5. $P_{2}$ has a 2.0GHz clock rate and CPI of 1.2. $P_{3}$ has a 4.0GHz clock rate and has a CPI of 2.2.

###### (a) Which processor has the highest performance expressed in instructions per second?
Performance of $P_{1}$ (instructions/sec) = $\frac{\text{Clock cycle}}{\text{time}}\times\frac{\text{Instruction count}}{\text{Clock cycle}}=\frac{\text{Clock rate}}{\text{CPI}}=\frac{3\times 10^{9}}{1.5}=2\times 10^{9}$
Performance of $P_{2}$ = $\frac{2\times 10^{9}}{1.2} \approx 1.67\times 10^{9}$
Performance of $P_{3}$ = $\frac{4 \times 10^{9}}{2.2} \approx 1.82 \times 10^{9}$
Therefore, performance of $P_{1}$ has the highest performance expressed in instructions per second.
###### (b) If the processors each execute a program in 10 seconds, find the number of cycles and the number of instructions.
Cycles of $P_{1}$ = $\text{time}\times \text{Clock rate} = 30 \times 10^{9}$.
Cycles of $P_{2}$ = $20\times 10^{9}$
Cycles of $P_{3} = 40 \times 10^{9}$.
Number of instructions of $P_{1}$ = $\frac{\text{Cycles}}{\text{CPI}} = \frac{30\times 10^{9}}{1.5} = 20\times 10^{9}$.
Number of instructions of $P_{2}$ = $\frac{20\times 10^{9}}{1.2} \approx 16.67\times 10^{9}$.
Number of instructions of $P_{3}$ = $\frac{40\times 10^{9}}{2.2} \approx 18.18\times 10^{9}$.
##### 7. Consider the following processors $P_{1}$ and $P_{2}$. Note that $P_{1}$ and $P_{2}$ have different ISAs, thus the total number of instructions is different even if the application is written in the same high-level programming language.

| Processor | Clock frequency | CPI | Instruction count |
| :-------: | :-------------: | :-: | :---------------: |
|  $P_{1}$  |      3 GHz      | 2.5 | $3\times 10^{9}$  |
|  $P_{2}$  |      2 GHz      | 1.2 | $5\times 10^{9}$  |

###### (a) Find the execution time of each processor. Which processor exhibits the better performance?
$$
\begin{align}
\text{Total time of }P_{1} &= \frac{\text{Instruction count}\times\text{CPI}}{\text{Clock rate}} \\
&= \frac{7.5\times 10^{9}}{3\times 10^{9}} \\
&= 2.5(s)
\end{align}
$$
$$
\begin{align}
\text{Total time of }P_{2} &= \frac{\text{Instruction count}\times\text{CPI}}{\text{Clock rate}} \\
&= \frac{6\times 10^{9}}{2\times 10^{9}} \\
&= 3(s)
\end{align}
$$
So, $P_{1}$ is faster than $P_{2}$, $P_{1}$ has better performance than $P_{2}$.
###### (b) We may use MIPS (millions of instructions per second) to compare the performance of two different processors. Calculate MIPS for processors $P_{1}$ and $P_{2}$. Which processor has better performance only considering MIPS?

$$
\text{MIPS} = \frac{\text{Instruction count}}{\text{Execution time}\times 10^{6}}
$$
So,
$$
\begin{align}
\text{MIPS}_{A} = \frac{3\times10^{9}}{2.5\times 10^{6}} = 1200 \\
\text{MIPS}_{B} = \frac{5\times10^{9}}{3\times 10^{6}} \approx 1666.67
\end{align}
$$
Based solely on MIPS, processor $P_{2}$​ appears to have better performance, since it has a higher MIPS value.

###### (c) Please explain why we cannot use MIPS directly to compare the performance of processors.
Despite $P_{2}$ has higher MIPS, $P_{2}$ has longer execution time than $P_{1}$.
So, we cannot use MIPS directly to compare processor performance because MIPS does not account for differences in instruction sets (ISAs) and instruction complexity. Also, does not reflect the actual execution time or the amount of work done per instruction. MIPS can be misleading when instruction counts vary, as a higher MIPS does not necessarily mean faster execution. MIPS ignores crucial factors like CPI and clock frequency, providing an incomplete picture of performance.
Therefore, MIPS is an unreliable metric for cross-processor performance comparisons, especially when processors have different ISAs or when the instruction counts for the same program differ.
##### 8. Consider two different implementations of the same instruction set architecture. The instructions can be divided into four classes according to their CPI (classes A, B, C, and D). Consider the following two processors and an application.

$P_{1}$: Clock frequency = 2.0GHz, CPIs for each instruction class = 1, 2, 3, 3
$P_{2}$: Clock frequency = 3.0GHz, CPIs for each instruction class = 2, 2, 2, 2
Application:
Instruction count = $1.0\times 10^{6}$,
Fractions by instruction classes: class A = 20%, class B = 10%, class C = 40%, class D = 30%
###### (a) Which processor is faster: $P_{1}$ or $P_{2}$?
Class A: $2\times10^{5}$ instructions
Class B: $1\times10^{5}$ instructions
Class C: $4\times10^{5}$ instructions
Class D: $3\times10^{5}$ instructions.
Total time of $P_{1}$
$$
\begin{align}
\text{Total time of }P_{1} &= \frac{\text{Instruction count}\times\text{CPI}}{\text{Clock rate}} \\
&= \frac{\sum \text{CPI}_{i}\times \text{Instruction count}_{i}}{\text{Clock rate}} \\
&= \frac{(2+2+12+12)\times 10^{5}}{2\times 10^{9}} \\
&= 14\times 10^{-4}(s)
\end{align}
$$
Total time of $P_{2}$
$$
\begin{align}
\text{Total time of }P_{2} &= \frac{(4+2+8+6)\times 10^{5}}{3\times 10^{9}} \\
&\approx 6.67\times 10^{-4}(s)
\end{align}
$$
Therefore, processor $P_{2}$ is faster than $P_{1}$.
###### (b) What is the global CPI for each implementation?
$$
\begin{align}
\text{Weighted average CPI of }P_{1} &= \sum (\text{CPI}_{i}\times \text{Fractions by instruction class}_{i}) \\
&= 1\times 0.2+ 2\times 0.1 + 3\times 0.4+ 3\times 0.3 \\
&= 2.5
\end{align}
$$
$$
\begin{align}
\text{Weighted average CPI of }P_{2} &= 2\times 0.2+ 2\times 0.1 + 2\times 0.4+ 2\times 0.3 \\
&= 2.0
\end{align}
$$
###### (c) Figure out the clock cycles required in both cases.
$$
\begin{align}
\text{Clock cycles of }P_{1} &= \sum (\text{CPI}_{i}\times \text{Instruction count}_{i}) \\
&= 1\times 2\times 10^{5} +2\times 1\times 10^{5} +3\times 4\times 10^{5} +3\times 3\times 10^{5}\\
&= 28 \times 10^{5}
\end{align}
$$
$$
\begin{align}
\text{Clock cycles of }P_{2} &= \sum (\text{CPI}_{i}\times \text{Instruction count}_{i}) \\
&= 2\times 2\times 10^{5} +2\times 1\times 10^{5} +2\times 4\times 10^{5} +2\times 3\times 10^{5}\\
&= 20 \times 10^{5}
\end{align}
$$
##### 9. Consider a computer running a program that requires 250 sec, with 40 sec spent executing INT instructions, 80 sec spent executing FP (floating-point) instructions, 80 sec executed load/store instructions, and 50 sec spent executing branch instructions.
###### (a) By how much is the total time reduced if the time for FP operations is reduced by 20%?
If the time for FP operations is reduced by 20%, time spent for executing FP is 64 second. So, total reduced time is 16 sec.
###### (b) Let us assume that the total execution time is reduced by 10% thanks to the reduced INT execution time. By how much is the time for INT operations reduced?
Reduced time is 10% of 250sec = 25sec. We spent 40 sec for INT instructions originally,
$$
\frac{25}{40}\times 100\% = 62.5\%
$$
is reduced for INT execution time.
##### 10. Assume that for a certain program compiler $A$ results in a dynamic instruction count of $1.1\times 10^{9}$ and has an execution time of 1.2 sec, while compiler $B$ results in a dynamic instruction count of $1.5\times10^9$ and an execution time of 1.7 sec.

###### (a) Find the average CPI for each program given that the processor has a clock cycle time of 1 ns.
$$
\text{CPI} = \frac{\text{Execution time}\times \text{Clock rate}}{\text{Instructions}}
$$
Therefore,
$$
\begin{align}
\text{CPI}_{A} &= \frac{1.2\times 10^{9}}{1.1\times 10^{9}} \approx 1.09 \\
\text{CPI}_{B} &= \frac{1.7\times 10^{9}}{1.5\times 10^{9}} \approx 1.13
\end{align}
$$
###### (b) Assume that the compiled programs run on two different processors $X$ and $Y$. If the execution times on the two processors are the same, how much faster is the clock of the processor $Y$ running compiler $B$’s code versus the clock of the processor $X$ running compiler $A$’s code? Assume that the processors have the same microarchitecture deploying the same ISA.

On same program, compiler $A$ results $1.1\times 10^{9}$ instructions and compiler $B$ results $1.5\times 10^{9}$ instructions.
$$
\begin{align}
\text{CPU}_{X}\text{ Time} &= \text{CPU}_{Y}\text{ Time} \\
\frac{\text{Instruction count}_{A}\times \text{CPI}_{A}}{\text{Clock rate}_{X}} &= \frac{\text{Instruction count}_{B}\times \text{CPI}_{B}}{\text{Clock rate}_{Y}} \\
\frac{\text{Clock rate}_{Y}}{\text{Clock rate}_{X}} &= \frac{\text{Instruction count}_{B}\times \text{CPI}_{B}}{\text{Instruction count}_{A}\times \text{CPI}_{A}} \\
&= \frac{1.7}{1.2} \approx 1.42
\end{align}
$$
So, clock rate of processor $Y$ is 1.42 times faster than clock rate of processor $X$.

###### (c) A new compiler is developed that uses only $5.0\times10^8$ instructions and has average CPI of 1.1. What is the speedup of using this new compiler versus using compiler $A$ or $B$ on the original processor?

Assume that a program is running on same processor. So, we can only consider CPI and instruction count.
$$
\begin{align}
\frac{T_{A}}{T_{new}} &= \frac{\text{Instruction count}_{A}\times\text{CPI}_{A}}{\text{Instruction count}_{new}\times\text{CPI}_{new}} = \frac{1.2\times10^{9}}{5.5\times 10^{8}} \\
&\approx 2.18 \\
\frac{T_{B}}{T_{new}} &= \frac{1.7\times10^{9}}{5.5\times 10^{8}} \\
&\approx 3.09
\end{align}
$$
New compiler is 2.18 times faster than $A$, 3.09 times faster than $B$.
