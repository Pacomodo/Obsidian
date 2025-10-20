1. Complete the provided modules (i.e. test1.sv, test2.sv, test3.sv, and test4.sv). Simulate each module using the provided testbench. You don’t need to modify the testbench modules. Capture the waveform of each design. You need to make the waveforms displayed until 45 ns. Your waveforms should include input and output signals of your design. Embed the captured images in the report document.
```systemverilog
// test1.sv
/* *******************************
 *      COSE221 Lab #2
 *
 *      Author: Gunjae Koo (gunjaekoo@korea.ac.kr)
 *
 * *******************************
 */
module test1(a, b, y, good);
        input                   a, b, y;
        output                  good;

        assign good = ((~a)&y) | ((~b)&y) | (a&b&(~y));
endmodule
```
This is testbench result of test1.sv.
![[Pasted image 20240520192913.png]]
___
```systemverilog
/* *******************************
 *      COSE221 Lab #2
 *
 *      Author: Gunjae Koo (gunjaekoo@korea.ac.kr)
 *
 * *******************************
 */
// A 2:1 multiplexer needs to be implemented using a ternary operator of SystemVerilog.

`timescale 1ns/1ps

module test2(a, b, y, good);
        input                   a, b, y;
        output                  good;

        logic                   n1, n2, n3;

        assign n1 = y ? 0: 1;
        assign n2 = b ? y: y;
        assign n3 = b ? n1: y;
        assign good = a ? n3: n2;

endmodule
```
This is testbench result of test2.sv.
![[Pasted image 20240520195355.png]]
___
```systemverilog
/* *******************************
 *      COSE221 Lab #2
 *
 *      Author: Gunjae Koo (gunjaekoo@korea.ac.kr)
 *
 * *******************************
 */
// Note that a 4:1 multiplexer can be implemented using a case statement.

`timescale 1ns/1ps

module test3(a, b, y, good);
        input                   a, b, y;
        output                  good;

        logic                   good;

        always_comb begin
                case ({a, b})
		                2'b00: good = y;
		                2'b01: good = y;
		                2'b10: good = y;
		                default: good = ~y;
                endcase
        end

endmodule
```
This is testbench result of test3.sv.
![[Pasted image 20240520202212.png]]
___
```systemverilog
/* *******************************
 *      COSE221 Lab #2
 *
 *      Author: Gunjae Koo (gunjaekoo@korea.ac.kr)
 *
 * *******************************
 */
/*
The test block can be implemented with a structural model by instantiating multiple submodules.
Please complete the provided test4 module that implements the structural model of the test2 module (i.e. the schematic in Section 3). Note that a 2:1 multiplexer can be implemented using tristate logic. You need to first complete mux2 module that implements a 2:1 multiplexer using tristate logic, then complete the structural module of test4. Please be advised that the output of tristate logic should be a tri type signal. 
*/

`timescale 1ns/1ps

module tristate(a, en, y);
        input                   a, en;
        output  tri             y;

        assign y = (en) ? a: 1'bZ;
endmodule

module mux2(a, b, sel, y);
        input                   a, b, sel;
        output  tri             y;

        tristate u_tristate_0 (a, ~sel, y);
        tristate u_tristate_1 (b, sel, y);

endmodule

module test4(a, b, y, good);
        input                   a, b, y;
        output  tri             good;

        tri                             n1, n2, n3;
        
        mux2 m1 (1'b1, 1'b0, y, n1);
        mux2 m2 (y, y, b, n2);
        mux2 m3 (y, n1, b, n3);
        mux2 m4 (n2, n3, a, good);


endmodule
```
This is testbench result of test4.sv.
![[Pasted image 20240520204712.png]]
___
2. Figure out the basic logic gate in the BLACKBOX module that can be verified using the test block. Namely, the output GOOD will become ‘1’ if the logic gate works correctly. You need to answer the name of the logic gate in the BLACKBOX module in the report document. 
![[Pasted image 20240520205605.png|center|300]]
This test block karnaugh map shows that BLACKBOX module works correctly when $A$ and $B$ are both $1$ then $Y = 0$, otherwise, $Y = 1$.
So, we can draw the truth table of BLACKBOX module.

| $A$ | $B$ | $Y$ |
| :-: | :-: | :-: |
|  0  |  0  |  1  |
|  0  |  1  |  1  |
|  1  |  0  |  1  |
|  1  |  1  |  0  |
This shows that BLACKBOX module is same as NAND gate.
___