___
##### 1. Given the input waveforms shown in the below figure, sketch the output, Q, of an SR latch. Ignore the delay of the latch.
![[Pasted image 20240617133453.png]]
Note that SR Latch is invalid state when S=1 and R=1.

##### 2. Given the input waveforms shown in the below figure, sketch the output, Q, of a D latch. Ignore the delay of the latch.
![[Pasted image 20240617150832.png]]
Note that D Latch is opaque when clk = 0 and transparent when clk = 1.

##### 3. Given the input waveforms shown in the below figure, sketch the output, Q, of a D flip-flop. Ignore the delay of the flip-flop.
![[Pasted image 20240617151139.png]]
Note that D flip-flop is edge-triggered.

##### 4. Consider the following state machine for this problem. Figure out the following state machine is a Moore FSM or a Mealy FSM. Using a binary state encoding (i.e. S0=”00”, S1=”01”, and S2=”10”), complete a state transition table and output table for the FSM. Write Boolean equations for the next state logic and the output logic.
![[Pasted image 20240617151216.png]]
Note that Moore FSM determines outputs only by current state. On the other hand, Mealy FSM determines outputs by current state and inputs. This state diagram determines output by current state and input, so, this state machine is Mealy FSM.
We can make state transition table and output table for the FSM.

| current state 0 | current state 1 |  A  |  B  | next state 0 | next state 1 | output |
| :-------------: | :-------------: | :-: | :-: | :----------: | :----------: | :----: |
|        0        |        0        |  1  |  X  |      0       |      1       |   0    |
|        0        |        0        |  0  |  X  |      0       |      0       |   0    |
|        0        |        1        |  X  |  1  |      1       |      0       |   0    |
|        0        |        1        |  X  |  0  |      0       |      0       |   0    |
|        1        |        0        |  1  |  1  |      1       |      0       |   1    |
|        1        |        0        |  1  |  0  |      0       |      0       |   0    |
|        1        |        0        |  0  |  1  |      0       |      0       |   0    |
|        1        |        0        |  0  |  0  |      0       |      0       |   0    |
$$
\begin{align}
\text{next state 0} &= \text{(current state 1)}B + \text{(current state 0)}AB\\
\text{next state 1} &= (\overline{\text{current state 0}})(\overline{\text{current state 1}})A\\
\text{output} &= (\text{current state 0})\overline{(\text{current state 1})}AB
\end{align}
$$
Above is boolean equation of FSM.

##### 5. Analyze the FSM shown in the figure below. X is an input, and Q is an output of the FSM. Figure out the following state machine is a Moore FSM or a Mealy FSM. Write the state transition and output tables for the FSM. Sketch the state transition diagram.
![[Pasted image 20240617154741.png]]
This FSM determines output only current state $S_{1}$, so, Moore FSM.
State transition table is below.

| $S_{1}$ | $S_{0}$ | $X$ | $S_{1}'$ | $S_{0}'$ |
| :-----: | :-----: | :-: | :------: | :------: |
|    0    |    0    |  0  |    0     |    1     |
|    0    |    0    |  1  |    1     |    1     |
|    0    |    1    |  0  |    0     |    0     |
|    0    |    1    |  1  |    1     |    0     |
|    1    |    X    |  X  |    0     |    1     |

Output table is below.

| $S_{1}$ | $S_{0}$ | $Q$ |
| :-----: | :-----: | :-: |
|    0    |    0    |  0  |
|    1    |    0    |  1  |
|    0    |    1    |  1  |
|    1    |    1    |  1  |
State transition diagram is below.
![[fig1.png]]
##### 6. Analyze the FSM shown in the figure below. A is an input, and Q is an output of the FSM. Figure out the following state machine is a Moore FSM or a Mealy FSM. Write the state transition and output tables for the FSM. Sketch the state transition diagram.
![[Pasted image 20240617155740.png]]
This FSM determines output only current state $S_{2}$, so, Moore FSM.
This is output table.

| $S_{2}$ | $Q$ |
| :-----: | :-: |
|    0    |  0  |
|    1    |  1  |

This is state transition table.

| $S_{2}$ | $S_{1}$ | $S_{0}$ | $A$ | $S_{2}'$ | $S_{1}'$ | $S_{0}'$ |
| ------- | ------- | ------- | --- | -------- | -------- | -------- |
| 0       | 0       | 1       | 0   | 0        | 0        | 1        |
| 0       | 0       | 1       | 1   | 0        | 1        | 0        |
| 0       | 1       | 0       | 0   | 0        | 0        | 1        |
| 0       | 1       | 0       | 1   | 1        | 0        | 0        |
| 1       | 0       | 0       | 0   | 0        | 0        | 1        |
| 1       | 0       | 0       | 1   | 1        | 0        | 0        |

This is state transition diagram.

![[fig2.png]]

##### 7. You are designing a 2-bit adder. The adder is built from two full adders as shown in the figure below. Your adder has input and output registers and must complete the addition within one clock cycle. The timing specifications of the full adder and the D flip-flop are listed in the following table.
|        Path        |  tpd  |  tcd  |
| :----------------: | :---: | :---: |
|    Cin --> Cout    | 20 ps | 15 ps |
|  Cin --> Sum (S)   | 25 ps | 15 ps |
|  A or B --> Cout   | 25 ps | 22 ps |
| A or B --> Sum (S) | 30 ps | 22 ps |

| D flip-flop | tsetup | thold | tpcq  | tccq  |
| :---------: | :----: | :---: | :---: | :---: |
|   Timing    | 30 ps  | 10 ps | 35 ps | 21 ps |

![[Pasted image 20240617155948.png|center]]
(a) If there is no clock skew, what is the maximum operating frequency of the circuit?
Note that maximum propagation delay is (AorB -> Cout) + (Cin -> Sum(S)) = 50ps.
So, $T_{c} \geq t_{pcq}+t_{pd}+t_{setup} \geq 115\text{ps}$.
So, maximum frequency $f = \frac{1}{115\text{ps}}=8.70\text{ GHz}$

(b) How much clock skew can the circuit tolerate if it must operate at 8 GHz?
$T_{c}\geq t_{pcq}+t_{pd}+t_{setup}+t_{skew}$
$T_{c}-(t_{pcq}+t_{setup}+t_{pd})\geq t_{skew}$
$125\text{ps}-115\text{ps}=10\text{ps}\geq t_{skew}$
So, $10\text{ps}$ can tolerate.

(c) How much clock skew can the circuit tolerate before it might experience a hold time violation?
$t_{skew} < (t_{ccq} + t_{cd}) - t_{hold}$
$t_{skew} < (21+15-10)\text{ps}=26\text{ps}$.
So, $26\text{ps}$ can tolerate.