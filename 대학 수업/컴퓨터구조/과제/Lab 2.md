(a) Here is myname.c code.
```C++
#include <stdio.h> 
 
int main() { 
    printf("Yeyoung Park\n"); 
    return 0; 
} 
```
I compiled this C code using below command, and run the generated binary file using Spike by below command. Here is the capture.
![[Pasted image 20241012231722.png]]
I generated an assembly file (myname.s) and a disassembled dump file (myname.dump) using below command. Here is the capture.
![[Pasted image 20241012232316.png]]
(...)
![[Pasted image 20241012232338.png]]
(b)
I compiled this C code using below command. I generated an assembly file (acc\_vec\_iter.s) and a disassembled dump file (acc\_vec\_iter.dump) using below command. Here is the capture.
![[Pasted image 20241012234440.png]]
To find the start point of the main function, I run this command.
```
cat acc_vec_iter.dump
```
![[Pasted image 20241012234824.png]]
I know that the start point of the main function 0x00010094 and end point of the main function is 0x0001012c.
So, I runed spike to the end point.
![[Pasted image 20241013000151.png]]
