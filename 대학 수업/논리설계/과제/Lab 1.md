![[tb_nor2.png]]
nor2 module에 대한 코드는 다음과 같습니다.
```systemverilog
module nor2 (a, b, c); 
    input           a, b; 
    output          c; 
 
    assign c = a ~| b; 
endmodule 
```
이에 대한 testbench 코드는 다음과 같습니다.
```systemverilog
`timescale 1ns/1ps 
 
module tb_nor2 (); 
 
    logic           a, b, c; 
 
    initial begin 
        $dumpfile("tb_nor2.vcd"); 
        $dumpvars(0, tb_nor2); 
 
        a = 'b0; b = 'b0; 
        #(10) a = 1'b0; b = 1'b0; 
        #(10) a = 1'b0; b = 1'b1; 
        #(10) a = 1'b1; b = 1'b0; 
        #(10) a = 1'b1; b = 1'b1; 
        #(10) 
        $finish; 
    end 
 
    nor2 dut (a, b, c); 
endmodule 
```
nor2모듈에 따르면 다음과 같은 truth table에 따라 결과가 나옴을 확인할 수 있습니다.

|  a  |  b  |  c  |
| :-: | :-: | :-: |
|  0  |  0  |  1  |
|  0  |  1  |  0  |
|  1  |  0  |  0  |
|  1  |  1  |  0  |
