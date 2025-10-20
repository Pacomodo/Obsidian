ISA가 뭐임?
ISA는 instruction set architecture. 
Instruction set은 instruction들을 모아놓은 건데, 이건 소프트웨어랑 하드웨어 사이를 잇는 일종의 Interface역할을 한다.
그래서 Instruction을 Processor가 받으면 Processor는 그 instruction을 실행시켜서 레지스터나 메인 메모리의 상태를 바꾼다.
예를 들어,
```
add x1, x2, x3
ld x1, x2(0)
and x1, x2, x3
```
같은 instruction들이 있다고 치면 x1의 데이터가 바뀌었다. (Change of states)
ISA는 CPU의 종류를 정의하게 한다. 그래서 ISA는 단순히 instruction의 모음이 아니라 메모리를 보는 CPU의 관점, 레지스터 넘버랑 역할 등등을 포함한다.
ISA는 소프트웨어랑 하드웨어 사이의 Contract(계약, 약속)이라고 보면 된다.
ISA $\neq$ CPU architecture(마이크로 아키텍쳐)이다.
skylake랑 ruptorlake는 다른 마이크로 아키텍쳐를 가졌지만 같은 x86 ISA를 가지고 있다.
우리가 사용하는 ISA는 RISC-V ISA로 RISC는 reduced instruction set computer라는 뜻이다.
instruction의 개수가 적다. simple하고 clean하다.
이와는 반대로 cisc가 있는데 이건 x86이 대표적 예시다. 이건 복잡하다.
x86의 경우 1~15byte의 instruction length를 가지는 반면 risc는 4byte를 가지고 있다.
우리가 사용하는 종류는 RV32I고, 32비트 컴퓨터 위에서 동작한다.
그 이외의 확장 옵션은 MAFDGQ등이 있는데, G는 general로, IMAFD를 모두 포함한다.
M은 integer multiply/divide 옵션을 지원하고 A는 아토믹 메모리 오퍼레이션, F는 싱글 float, D는 double float Q는 quad float이다.
high-level은 컴파일러를 통해 assembly로 바뀌고 assembler를 통해 0과 1로만 이루어진 binary file이 생성된다. 이 program file은 메인 메모리에 저장이 된다.
근데 0과 1이 섞여 있어서, instruction과 data가 구분이 안된다. CPU는 SSD같은 곳에 저장되있는 program을 불러와서 실행시킨다.
```
10074: fd010113   add sp, sp, -48
```
이라고 하면, 10074는 메모리 주소(program counter, PC)이고 fd010113은 16진법으로 표시된 machine code, 가장 오른쪽은 그것이 어떤 의미를 담았는지 표현하는 assembly이다.
주소 하나에 1byte=8bit의 정보를 담는다.
32bit computer는 주소의 길이가 32bit = $2^{32}$개의 주소라는 뜻으로, 4GB의 메모리가 있다.
그니깐 이걸 16진법으로 표현하면 0x00000000부터 0xFFFFFFFF까지.
