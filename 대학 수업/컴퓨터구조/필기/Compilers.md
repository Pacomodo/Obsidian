memory map = range of address assigned to a certain instruction or data in binary file.
맨 처음엔 exception handler가 깔리고 그 위에는 text(instruction) 그 위에는 전역변수(global data)그 위에는 dynamic data(stack + heap), 그 위에는 OS&I/O.
구체적인 예시는 PPT를 참고하면 될듯
hello.c라는 c program이 있어. 컴파일러를 통해 hello.s라는 어셈블리 코드가 생성돼. 그건 어셈블러를 통해 object file이 생성돼.(hello.o) hello world에는 printf라는 함수가 있는데 그건 stdio.h에 정의되어있으므로 링커가 object file들을 잘 묶어. 그래서 executable한 program을 생성해. 일반적으로 이건 static linking이고, dynamic linking은 호출될 때만 링커가 그때그때 묶는거
ISA같고 Program같으면 CPI같음? 정답은 NO임. Compiler의 optimizing option에 따라 다르다.
알고리즘에 따라서도 퍼포먼스 다르고 언어에 따라서도 퍼포먼스 다르다
ISA Design Principle
Simplicity favors regularity
예를 들어 add a, b, c로 표현하지, add3 6, 1, 2, 3으로 표현하지 않는다.
add : operation
a : destination operand
b,c : source operand
일정한 instruction format
같은 operand개수(two source, one destination)
여러개의 code는 여러개의 instruction으로 쪼개진다.
Make the common case fast.
복잡한 instruction(less common) performed using multiple simple instructions
