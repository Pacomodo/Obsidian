##### 1. Write a Boolean equation in a sum-of-products canonical form for each of the following truth table.
###### (a)

|  A  |  B  |  Y  |
| :-: | :-: | :-: |
|  0  |  0  |  0  |
|  0  |  1  |  1  |
|  1  |  0  |  0  |
|  1  |  1  |  1  |
$\bar{A}B+AB = \sum(1,3)$
###### (b)

|  A  |  B  |  C  |  Y  |
| :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  0  |
|  0  |  0  |  1  |  1  |
|  0  |  1  |  0  |  1  |
|  0  |  1  |  1  |  1  |
|  1  |  0  |  0  |  1  |
|  1  |  0  |  1  |  0  |
|  1  |  1  |  0  |  0  |
|  1  |  1  |  1  |  0  |
$\bar{A}\bar{B}C+\bar{A}B\bar{C}+\bar{A}BC+A\bar{B}\bar{C} = \sum(1,2,3,4)$
###### (c)

|  A  |  B  |  C  |  Y  |
| :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  0  |
|  0  |  0  |  1  |  1  |
|  0  |  1  |  0  |  0  |
|  0  |  1  |  1  |  0  |
|  1  |  0  |  0  |  1  |
|  1  |  0  |  1  |  0  |
|  1  |  1  |  0  |  1  |
|  1  |  1  |  1  |  0  |
$\bar{A}\bar{B}C + A\bar{B}\bar{C} + AB\bar{C}=\sum(1,4,6)$
##### 2. Write a Boolean equation in a product-of-sums canonical form for each of the truth table in Q1.
###### (a)
$(A+B)(\bar{A}+B)=\prod(0,2)$
###### (b)
$(A+B+C)(\bar{A}+B+\bar{C})(\bar{A}+\bar{B}+C)(\bar{A}+\bar{B}+\bar{C})=\prod(0,5,6,7)$
###### (c)
$(A+B+C)(A+\bar{B}+C)(A+\bar{B}+\bar{C})(\bar{A}+B+\bar{C})(\bar{A}+\bar{B}+\bar{C})=\prod(0,2,3,5,7)$
##### 3. Sketch a combinational circuit in a sum-of-products canonical form using only NOT gates and AND and OR gates for each of the truth table in Q1.
###### (a)
![[SmartSelect_20240421_015402_Samsung Notes.jpg|center|400]]
###### (b)
![[SmartSelect_20240421_020719_Samsung Notes.jpg|center|400]]
###### (c)
![[SmartSelect_20240421_021419_Samsung Notes.jpg|center|400]]
##### 4. Sketch a combinational circuit in a sum-of-products canonical form using only NOT gates and NAND gates for each of the truth table in Q1.
###### (a)
![[SmartSelect_20240421_022142_Samsung Notes.jpg|center|400]]
###### (b)
![[SmartSelect_20240421_023516_Samsung Notes.jpg|center|400]]
###### (c)
![[SmartSelect_20240421_023735_Samsung Notes.jpg|center|400]]
##### 5. Sketch a combinational circuit in a product-of-sums canonical form using only NOT gates and NOR gates for each of the truth table in Q1.
###### (a)
![[SmartSelect_20240423_193227_Samsung Notes.jpg|center|400]]
###### (b)
![[SmartSelect_20240423_194501_Samsung Notes.jpg|center|400]]
###### (c)
![[SmartSelect_20240423_220800_Samsung Notes.jpg|center|400]]
##### 6. Simplify the Boolean equation for each of the following truth table using a K-map.
###### (a)

|  A  |  B  |  C  |  D  |  Y  |
| :-: | :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  0  |  1  |
|  0  |  0  |  0  |  1  |  1  |
|  0  |  0  |  1  |  0  |  0  |
|  0  |  0  |  1  |  1  |  0  |
|  0  |  1  |  0  |  0  |  1  |
|  0  |  1  |  0  |  1  |  1  |
|  0  |  1  |  1  |  0  |  0  |
|  0  |  1  |  1  |  1  |  0  |
|  1  |  0  |  0  |  0  |  0  |
|  1  |  0  |  0  |  1  |  0  |
|  1  |  0  |  1  |  0  |  1  |
|  1  |  0  |  1  |  1  |  1  |
|  1  |  1  |  0  |  0  |  0  |
|  1  |  1  |  0  |  1  |  0  |
|  1  |  1  |  1  |  0  |  1  |
|  1  |  1  |  1  |  1  |  1  |

![[SmartSelect_20240423_221821_Samsung Notes.jpg|center|300]]
$Y = \bar{A}\bar{C}+AC$
###### (b)

|  A  |  B  |  C  |  D  |  Y  |
| :-: | :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  1  |  0  |
|  0  |  0  |  1  |  0  |  0  |
|  0  |  0  |  1  |  1  |  1  |
|  0  |  1  |  0  |  0  |  0  |
|  0  |  1  |  0  |  1  |  0  |
|  0  |  1  |  1  |  0  |  1  |
|  0  |  1  |  1  |  1  |  1  |
|  1  |  0  |  0  |  0  |  1  |
|  1  |  0  |  0  |  1  |  1  |
|  1  |  0  |  1  |  0  |  1  |
|  1  |  0  |  1  |  1  |  1  |
|  1  |  1  |  0  |  0  |  0  |
|  1  |  1  |  0  |  1  |  0  |
|  1  |  1  |  1  |  0  |  0  |
|  1  |  1  |  1  |  1  |  0  |

![[SmartSelect_20240423_222546_Samsung Notes.jpg|center|300]]
 $Y = \bar{A}CD+\bar{A}BC+A\bar{B}$
##### 7. Simplify the following Boolean equations using Boolean theorems. You need to note the Boolean theorems used for each step.
###### (a) $Y=\bar{A}BC + \bar{A}B\bar{C}$
$$
\begin{align}
Y &= \bar{A}BC + \bar{A}B\bar{C} \\
\xrightarrow{\textrm{by distributivity}} &= \bar{A}B(C+\bar{C}) \\
\xrightarrow{\text{by complement}} &= \bar{A}B
\end{align}
$$
###### (b) $Y=\overline{ABC} + A\bar{B}$
$$
\begin{align}
Y&=\overline{ABC} + A\bar{B} \\
\xrightarrow{\text{De Morgan's Theorem}}&=\bar{A}+\bar{B}+\bar{C}+A\bar{B} \\
\xrightarrow{\text{by idempotency}}&=\bar{A}+1\cdot \bar{B}+\bar{C}+A\bar{B} \\
\xrightarrow{\text{by distributivity and commutativity}}&=\bar{A}+(1+A)\bar{B}+\bar{C} \\
\xrightarrow{\text{by null element}} &= \bar{A} + \bar{B}+\bar{C} \\
\xrightarrow{\text{De Morgan's law}} &= \overline{ABC}
\end{align}
$$
###### (c) $Y = ABC\bar{D} + A\overline{BCD} + \overline{(A+B+C+D)}$
$$
\begin{align}
Y &= ABC\bar{D} + A\overline{BCD} + \overline{(A+B+C+D)} \\
\xrightarrow{\text{De Morgan's Theorem}} &=ABC\bar{D} + A(\bar{B}+\bar{C}+\bar{D}) + \bar{A}\bar{B}\bar{C}\bar{D} \\
\xrightarrow{\text{distributivity}} &= ABC\bar{D} + A\bar{B}+A\bar{C}+A\bar{D}+\bar{A}\bar{B}\bar{C}\bar{D} \\
\xrightarrow{\text{distributivity and commutativity}} &= A\bar{D}(BC+1)+A\bar{B}+A\bar{C}+\bar{A}\bar{B}\bar{C}\bar{D} \\
\xrightarrow{\text{null element}} &= A\bar{D}+A\bar{B}+A\bar{C}+\bar{A}\bar{B}\bar{C}\bar{D} \\
\xrightarrow{\text{distributivity}} &= A\bar{D}+A\bar{B}+\bar{C}(A+\bar{A}\bar{B}\bar{D}) \\
\xrightarrow{\text{distributivity}} &= A\bar{D}+A\bar{B}+\bar{C}((A+\bar{A})(A+\bar{B}\bar{D})) \\
\xrightarrow{\text{complement and distributivity}} &= A\bar{D}+A\bar{B}+A\bar{C}+\bar{B}\bar{C}\bar{D} \\
\xrightarrow{\text{distributivity}} &=A(\bar{B}+\bar{C}+\bar{D})+\bar{B}\bar{C}\bar{D} \\
\xrightarrow{\text{De Morgan's Theorem}} &= A\overline{BCD}+\bar{B}\bar{C}\bar{D}
\end{align}
$$

##### 8. Using De Morgan equivalent gates and bubble pushing methods, redraw the circuits in the following figure. Write the Boolean equation after applying De Morgan’s theorem.
![[Pasted image 20240418194515.png|center]]
Note that **before** applying De Morgan's law, this figure has the boolean equation $Y = \overline{\overline{\overline{AB}\cdot\overline{CD}}\cdot E}$
We can redraw this figure using bubble pushing method and De Morgan equivalent gates.
![[SmartSelect_20240423_202125_Samsung Notes.jpg|center|400]]
So, **after** applying De Morgan's Theorem, the boolean equation is $Y = (\bar{A}+\bar{B})(\bar{C}+\bar{D})+\bar{E}$.
##### 9. Find a minimal Boolean equation for the following truth table using K-map.
###### (a)

|  A  |  B  |  C  |  D  |  Y  |
| :-: | :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  0  |  X  |
|  0  |  0  |  0  |  1  |  X  |
|  0  |  0  |  1  |  0  |  X  |
|  0  |  0  |  1  |  1  |  0  |
|  0  |  1  |  0  |  0  |  0  |
|  0  |  1  |  0  |  1  |  1  |
|  0  |  1  |  1  |  0  |  0  |
|  0  |  1  |  1  |  1  |  X  |
|  1  |  0  |  0  |  0  |  0  |
|  1  |  0  |  0  |  1  |  X  |
|  1  |  0  |  1  |  0  |  X  |
|  1  |  0  |  1  |  1  |  X  |
|  1  |  1  |  0  |  0  |  1  |
|  1  |  1  |  0  |  1  |  0  |
|  1  |  1  |  1  |  0  |  0  |
|  1  |  1  |  1  |  1  |  0  |

![[SmartSelect_20240423_223226_Samsung Notes.jpg|center|300]]
$Y = AB\bar{C}\bar{D}+\bar{A}\bar{C}D$
###### (b)

|  A  |  B  |  C  |  D  |  Y  |
| :-: | :-: | :-: | :-: | :-: |
|  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  1  |  1  |
|  0  |  0  |  1  |  0  |  X  |
|  0  |  0  |  1  |  1  |  X  |
|  0  |  1  |  0  |  0  |  0  |
|  0  |  1  |  0  |  1  |  X  |
|  0  |  1  |  1  |  0  |  X  |
|  0  |  1  |  1  |  1  |  X  |
|  1  |  0  |  0  |  0  |  1  |
|  1  |  0  |  0  |  1  |  0  |
|  1  |  0  |  1  |  0  |  0  |
|  1  |  0  |  1  |  1  |  1  |
|  1  |  1  |  0  |  0  |  0  |
|  1  |  1  |  0  |  1  |  0  |
|  1  |  1  |  1  |  0  |  X  |
|  1  |  1  |  1  |  1  |  1  |

![[SmartSelect_20240423_224250_Samsung Notes.jpg|center|300]]
$Y=CD+\bar{A}D+A\bar{B}\bar{C}\bar{D}$
