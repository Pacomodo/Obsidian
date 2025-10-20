###### Problem 1.
```
slli x30, x5, 2
# x30에 x5에 저장된 값(f)을 왼쪽으로 비트쉬프트 두번 해서 저장해
add x30, x10, x30
# x30에 x10에 저장된 값(A의 base address)를 더해줘
# 여기까지 하면 x30에 저장된 결과는 A의 base address + f*4야.
slli x31, x6, 2
# x31에 x6에 저장된 값(g)을 왼쪽으로 비트쉬프트 두번 해서 저장해
add x31, x11, x31
# x31에 x11에 저장된 값(B의 base address)를 더해줘
# 여기까지 하면 x31에 저장된 결과는 B의 base address + g*4야.
lw x5, 8(x30)
# x5에 (x30에 저장된 값 + 8)만큼의 주소를 가진 메모리의 값을 저장해
# x5에 저장되는 값은 Mem[&A[0] + 4*f + 4*2]야.
# 다시 말하면, x5에 저장되는 값은 A[f+2]야
addi x12, x30, 16
# x12에 x30에 저장된 값(&A[0] + f*4) + 16(4*4)를 저장해
lw x30, 0(x12)
# x30에 x12(&A[0] + f*4 + 4*4)의 주소를 가진 메모리의 값을 저장해
# x30에 저장되는 값은 A[f+4]야
add x30, x30, x5
# x30에 A[f+4] + A[f+2]를 저장해
slli  x30, x30, 3
# 그걸 왼쪽으로 세번 비트쉬프트 해
# x30 = 8*(A[f+2] + A[f+4])야.
sw x30, -8(x31)
# 이제 그걸 ((x31에 저장된 값) - 8)만큼의 주소를 가진 메모리에 저장해.
# x31에 저장된 값은 (B의 base address + g*4)야
# 8 = 4*2야
# 그러니까 ((x31에 저장된 값) - 8) = (B의 base address + (g-2))야
 ```
 결론적으로 정리하면 이렇게 코드를 작성할 수 있어.

```C
B[g-2] = 8*(A[f+2] + A[f+4]);
```

###### Problem 2.
```
addi x30, x10, 16
# x30에 x10에 저장된 값 + 16을 저장해줘.
# x30 = (A의 base address + 4*4)가 돼.
addi x31, x10, 8
# x31에 x10에 저장된 값 + 8을 저장해줘
# x31 = (A의 base address + 4*2)가 돼.
sw x31, 0(x30)
# x31에 저장된 값을 x30의 주소를 가진 메모리에 저장해
# A[4] = &A[2]
lw x30, 0(x30)
# x30의 주소를 가진 메모리의 값을 x30으로 가져와
add x30, x30, x31 
# 거기에 x31에 저장된 값을 더해
addi x6, x30, -12
# x6(g)에 x30의 값 - 12를 저장해
```
결론적으로 다음과 같이 변환할 수 있다.
```C
g = &A[2] + &A[2] - 12;
```
###### Problem 3.
(a)
```assembly
addi x6, zero, 15
Loop: slli x28, x6, 2 # x28에 4*i를 저장해
add x29, x10, x28 # x29에 A의 base address + 4*i를 저장해
lw x5, 0(x29) # x5(f)에 A[i]를 저장해
add x30, x11, x28 # x30에 B의 base address + 4*i를 저장해
lw x31, 0(x30) # x31에 B[i]를 저장해
sw x31, 0(x29) # x31의 값을 A[i]에 저장해
sw x5, 0(x30) #f의 값을 B[i]에 저장해
add x6, x6, -1 # i의 값을 하나 줄여
bge x6, zero, Loop #루프로 돌아가
```
(b)
```assembly
# 편의 상 x28은 pA, x29는 pB로 둘거야
addi x29, x11, 60 # pB = &B[15];
addi x28, x10, 60 # pA = &A[15];
Loop: lw x5, 0(x28) # pA가 가리키는 값을 x5(f)에 저장해
lw x30, 0(x29) # pB가 가리키는 값을 x30에 저장해
sw x30, 0(x28) # pA가 가리키는 값을 pB가 가리키는 값으로 바꿔
sw x5, 0(x29) # pB가 가리키는 값을 f가 가리키는 값으로 바꿔
# x5의 값을 Mem[x29+0]로 옮겨
add x29, x29, -4
add x28, x28, -4
bge x28, x10, Loop
```
(c)
A번 코드는 $1+9\times 16$번, B번 코드는 $2+7\times 16$번 반복되었다.
$T_{exe} = \text{Clock Period}\times \text{CPI}\times \text{Instruction count}$이므로, 나머지는 모두 같다는 전제 하에 Instruction count만 다르다. 따라서,
$$
\frac{145}{114} = 1.27
$$
약 27퍼 향상되었다.

###### Problem 4.
```assembly
addi x5, x0, 0 # x5은 0
addi x6, x0, 200 # x6은 200
LOOP: blt x6, x0, DONE # x6 < 0이니? 아니
addi x6, x6, -1 # x6은 199
addi x5, x5, 5 # x5는 5
jal x0, LOOP # 루프로 가가
DONE: 
```
(a) 이거 반복하면 1005됨.
(b)
```C
int i = 0;
for (j = 200; j >= 0; j--){
i += 5;
}
```

###### Problem 5.
```
0x0080 fact: addi sp, sp, -8 
0x0084 sw x1, 4(sp) 
0x0088 sw x10, 0(sp) 
0x008C addi x5, x10, -1 
0x0090 bge x5, x0, L1 
0x0094 addi x10, x0, 1 
0x0098 addi sp, sp, 8 
0x009C jalr x0, 0(x1) 
0x00A0 L1: addi x10, x10, -1 
0x00A4 jal x1, fact 
0x00A8 addi x6, x10, 0 
0x00AC lw x10, 0(sp) 
0x00B0 lw x1, 4(sp) 
0x00B4 addi sp, sp, 8 
0x00B8 mul x10, x10, x6 
0x00BC jalr x0, 0(x1)
```
(a)
Basic block의 정의는?
끝 지점을 제외한 Branch가 존재하지 않고,
시작 지점을 제외한 Target이 존재하지 않는
Instruction의 sequence를 basic block이라고 한다.

이 정의에 따르면...
0x0080부터 0x0090(bge라는 branch 존재)
0x0094부터 0x009C(jalr라는 branch)
0x00A0(L1이라는 target)부터 0x00A4(jal라는 branch)
0x00A8부터 0x00BC(jalr라는 branch)
총 4개

