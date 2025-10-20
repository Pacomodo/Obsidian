___
1. Complete the provided design files (i.e. rca16.sv and cla16.sv). You can complete “/* FILL THIS */” parts in the provided files.  You can verify your design using the provided testbench modules that can perform self-checking for DUT.
___
```systemverilog
/* *******************************
 *      COSE221 Lab #4
 *
 *      Author: Gunjae Koo (gunjaekoo@korea.ac.kr)
 *
 * *******************************
 */

`timescale 1ns/1ps
// full adder (structural module)
module fadd (
        input   logic   a, b, cin,
        output  logic   s, cout
);

        logic   [3:0]   n;      // internal nodes

        // sum: s = (a ^ b) ^ cin
        xor2    u_xor2_0        (a, b, n[0]);
        xor2    u_xor2_1        (n[0], cin, s);

        // cout: cout = (a*b) + (a*cin) + (b*cin)
        and2 u_and2_0 (a, b, n[1]);
        and2 u_and2_1 (a, cin, n[2]);
        and2 u_and2_2 (b, cin, n[3]);
        or3 u_or3_0 (n[1], n[2], n[3], cout);


endmodule

module rca16 (
        input                   clk, rst_b,
        input   logic [15:0]    a, b,
        input   logic           cin,
        output  logic [15:0]    s,
        output  logic           cout
);

        // registers for input signals
        logic   [15:0]  a_q, b_q;
        logic                   cin_q;

        // t_pcq of D flip-flop is 0.010 ns
        always_ff @ (posedge clk or negedge rst_b) begin
                if (~rst_b) begin
                        a_q <= 'b0;
                        b_q <= 'b0;
                        cin_q <= 'b0;
                end else begin
                        a_q <= #(0.010) a;
                        b_q <= #(0.010) b;
                        cin_q <= #(0.010) cin;
                end
        end

        logic   [15:0]  c;              // internal nodes (carry)
        logic   [15:0]  s_w;    // sum (output of an adder)

        fadd    u_fadd_0        (a_q[0],  b_q[0],  cin_q, s_w[0],  c[0]);
        fadd    u_fadd_1        (a_q[1],  b_q[1],  c[0], s_w[1],  c[1]);
        fadd    u_fadd_2        (a_q[2],  b_q[2],  c[1], s_w[2],  c[2]);
        fadd    u_fadd_3        (a_q[3],  b_q[3],  c[2], s_w[3],  c[3]);
		fadd    u_fadd_4        (a_q[4],  b_q[4],  c[3], s_w[4],  c[4]);
		fadd    u_fadd_5        (a_q[5],  b_q[5],  c[4], s_w[5],  c[5]);
		fadd    u_fadd_6        (a_q[6],  b_q[6],  c[5], s_w[6],  c[6]);
		fadd    u_fadd_7        (a_q[7],  b_q[7],  c[6], s_w[7],  c[7]);
		fadd    u_fadd_8        (a_q[8],  b_q[8],  c[7], s_w[8],  c[8]);
		fadd    u_fadd_9        (a_q[9],  b_q[9],  c[8], s_w[9],  c[9]);
		fadd    u_fadd_10       (a_q[10], b_q[10], c[9], s_w[10], c[10]);
		fadd    u_fadd_11       (a_q[11], b_q[11],c[10], s_w[11], c[11]);
		fadd    u_fadd_12       (a_q[12], b_q[12],c[11], s_w[12], c[12]);
		fadd    u_fadd_13       (a_q[13], b_q[13],c[12], s_w[13], c[13]);
		fadd    u_fadd_14       (a_q[14], b_q[14],c[13], s_w[14], c[14]);
		fadd    u_fadd_15       (a_q[15], b_q[15],c[14], s_w[15], c[15]);
        // registers for output signals
        always_ff @ (posedge clk or negedge rst_b) begin
                if (~rst_b) begin
                        s <= 'b0;
                        cout <= 'b0;
                end else begin
                        s <= #(0.010) s_w;
                        cout <= #(0.010) c[15];
                end
        end
endmodule
```
![[Pasted image 20240617222705.png]]

```systemverilog
/* *******************************
 *      COSE221 Lab #4
 *
 *      Author: Gunjae Koo (gunjaekoo@korea.ac.kr)
 *
 * *******************************
 */
`timescale 1ns/1ps
module fadd_cla (
        input   logic   a, b, cin,
        output  logic   p, g, s
);
        logic n; // internal node
        // propagate: p = a+b
        or2   u_or2_0    (a, b, p);
        // generate: g = a*b
        and2  u_and2_0   (a, b, g);
        // sum: sum = (a ^ b) ^ cin
        xor2  u_xor2_0   (a, b, n);
        xor2  u_xor2_1   (n, cin,s);
endmodule

// carry lookahead logic (4-bit)
module cll4 (
        input   logic   [3:0]   p, g,
        input   logic           cin,
        output  logic   [3:0]   cout
);
        logic  [11:0]  n; // internal nodes
        // cout[0] = g[0] + p[0]*cin
        and2   u_and2_0    (p[0], cin, n[0]);
        or2    u_or2_0     (g[0], n[0], cout[0]);
        // cout[1] = g[1] + p[1]*g[0] + p[1]*p[0]*cin
        and2   u_and2_1    (p[1], g[0], n[1]);
        and3   u_and3_0    (p[1], p[0], cin, n[2]);
        or3    u_or3_0     (g[1], n[1], n[2], cout[1]);
        // cout[2] = g[2] + p[2]*g[1] + p[2]*p[1]*g[0] + p[2]*p[1]*p[0]*cin
        and2   u_and2_2    (p[2], g[1], n[3]);
        and3   u_and3_1    (p[2], p[1], g[0], n[4]);
        and4   u_and4_0    (p[2], p[1], p[0], cin, n[5]);
        or4    u_or4_0     (g[2], n[3], n[4], n[5], cout[2]);
        // cout[3] = g[3:0] + p[3:0]*cin, g[3:0] = ??, p[3:0] = ??
        and2   u_and2_3    (p[3], g[2], n[6]);
        and3   u_and3_2    (p[3], p[2], g[1], n[7]);
        and4   u_and4_1    (p[3], p[2], p[1], g[0], n[8]);
        or4    u_or4_1     (g[3], n[6], n[7], n[8], n[9]);        // g[3:0]
		and4   u_and4_2    (p[3], p[2], p[1], p[0], n[10]);        // p[3:0]
        and2   u_and2_4    (n[10], cin, n[11]);
        or2    u_or2_1     (n[9], n[11], cout[3]);
endmodule

// 4-bit carry lookahead adder
module cla4 (
        input   logic [3:0]     a, b,
        input   logic           cin,
        output  logic [3:0]     s,
        output  logic           cout
);
        logic   [3:0]   p, g;
        logic   [3:0]   c;      // carry

        fadd_cla    u_fadd_cla_0    (a[0], b[0], cin, p[0], g[0], s[0]);
        fadd_cla    u_fadd_cla_1    (a[1], b[1], c[0], p[1], g[1], s[1]);
        fadd_cla    u_fadd_cla_2    (a[2], b[2], c[1], p[2], g[2], s[2]);
        fadd_cla    u_fadd_cla_3    (a[3], b[3], c[2], p[3], g[3], s[3]);
        cll4        u_cll4_0        (p, g, cin, c);
        assign cout = c[3];
endmodule

// 16-bit carry lookahead adder
module cla16 (
        input                   clk, rst_b,
        input   logic [15:0]    a, b,
        input   logic           cin,
        output  logic [15:0]    s,
        output  logic           cout
        );

        // registers for input signals
        logic   [15:0]  a_q, b_q;
        logic           cin_q;

        // t_pcq of D flip-flop is 0.010 ns
        always_ff @ (posedge clk or negedge rst_b) begin
                if (~rst_b) begin
                        a_q <= 'b0;
                        b_q <= 'b0;
                        cin_q <= 'b0;
                end else begin
                        a_q <= #(0.010) a;
                        b_q <= #(0.010) b;
                        cin_q <= #(0.010) cin;
                end
        end

        logic   [3:0]   c;      // internal nodes, carry-outs from cll4
        logic   [15:0]  s_w;    // sum of an adder

        cla4  u_cla4_0 (a_q[3:0], b_q[3:0], cin_q, s_w[3:0], c[0]);
        cla4  u_cla4_1 (a_q[7:4], b_q[7:4], c[0], s_w[7:4], c[1]);
        cla4  u_cla4_2 (a_q[11:8], b_q[11:8], c[1], s_w[11:8], c[2]);
        cla4  u_cla4_3 (a_q[15:12], b_q[15:12], c[2], s_w[15:12], c[3]);
        
        // registers for output signals
        always_ff @ (posedge clk or negedge rst_b) begin
                if (~rst_b) begin
                        s <= 'b0;
                        cout <= 'b0;
                end else begin
                        s <= #(0.010) s_w;
                        cout <= #(0.010) c[3];
                end
        end
endmodule
```
![[Pasted image 20240617233130.png]]
___
2. For each 16-bit adder design, figure out the shortest clock period that can generate correct results. You can check if your 16-bit adder design generates correct results by changing clock periods in the testbench modules. Figure out the clock periods in a 10 ps resolution (e.g. 230 ps not 234 ps). For this simulation setup, we ignore the setup time of a D flip-flop and clock skew of clock signals. Justify your answer. (Hint: consider when the setup time constraint is violated.)

We want to compute Cycle time Constraint.
So, we want to compute $t_{pcq}+t_{pd}$ for each adder.(Recall that we ignore $t_{setup}$).
Note that $t_{pd}$ for each gate are shown below table.

| xor2 | and2 | or2 | and3 | or3 | and4 | or4 |
| ---- | ---- | --- | ---- | --- | ---- | --- |
| 10   | 15   | 15  | 16   | 16  | 17   | 17  |

4bit CLA에 대해서 코드를 보면, p[3]을 보면, fadd cla에의해 or2, cll4에 의해 and4, or4, or2를 지나므로, 가장 긴 path는 15+15+17+17=64ps.
이게 4개 존재하므로, 256ps가 $t_{pd}$가 된다.
$t_{pcq} = 0.01\text{ns} = 10ps$이므로, 약 270ps가 cycle time constraint가 될 것이다.

마찬가지로, 16비트 rca에 대해선, and2, or3가 16번 반복되는것이 가장 긴 path이므로, $31\times 16 = 496ps$. $t_{pcq} = 10ps$이므로 약 510ps가 cycle time constraint가 될 것이다.