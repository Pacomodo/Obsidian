___
1. Complete the provided modules (i.e. fsm1.sv and fsm2.sv). Simulate each module using the provided testbench. You don’t need to modify the testbench modules. Capture the waveform of each design. You need to make the waveforms displayed until the end of simulation. Your waveforms should include all signals in the DUT (design under test) modules. For the factored FSM design, your waveform includes all internal signals in fsm_mode and fsm_light. Embed the captured images in the report document.
___
```systemverilog
/* *******************************
 *      COSE221 Lab #3
 *
 *      Author: Gunjae Koo (gunjaekoo@korea.ac.kr)
 *
 * *******************************
 */

module fsm1(
        input   clk,
        input   reset_n,        // asychronous negative reset
        input   ta, tb,
        output  [1:0]   la, lb
);
        logic   [1:0]   la, lb;

        localparam S0 = 2'b00,
                   S1 = 2'b01,
                   S2 = 2'b10,
                   S3 = 2'b11;

        localparam GREEN = 2'b00,
                  YELLOW = 2'b01,
                     RED = 2'b10;
        logic [1:0] state_curr, state_next;
        // state register
        always_ff @ (posedge clk or negedge reset_n)begin
	        if(~reset_n) begin
		        state_curr < = S0;
		    end else begin
			    state_curr < = state_next;
			end
		end
        // next state logic
        always_comb begin
	        case (state_curr)
		        S0: state_next = (ta) ? S0: S1;
		        S1: state_next = S2;
		        S2: state_next = (tb) ? S2: S3;
		        S3: state_next = S0;
		        default: state_next = S0;
		    endcase
		end
        // output logic
        always_comb begin
	        case (state_curr)
			    S0: {la, lb} = {GREEN, RED};
			    S1: {la, lb} = {YELLOW, RED};
			    S2: {la, lb} = {RED, GREEN};
			    S3: {la, lb} = {RED, YELLOW};
			    default: {la, lb} = {GREEN, RED};
			endcase
		end
        // synthesis translate_off
        logic [2*8-1:0] state_dbg;
        always_comb begin
            case (state_curr)
                S0: state_dbg = "S0";
                S1: state_dbg = "S1";
                S2: state_dbg = "S2";
                S3: state_dbg = "S3";
            endcase
        end
        // synthesis translate_on
endmodule
```
![[Pasted image 20240603204945.png]]
```systemverilog
/* *******************************
 *      COSE221 Lab #3
 *
 *      Author: Gunjae Koo (gunjaekoo@korea.ac.kr)
 *
 * *******************************
 */
module fsm2(
        input   clk,
        input   reset_n,        // asychronous negative reset
        input   p, r,
        input   ta, tb,
        output  [1:0] la, lb
);
        logic m;
        fsm_mode modfsm (clk, reset_n, p, r, m);
        fsm_light lightfsm (clk, reset_n, m, ta, tb, la, lb);
endmodule

module fsm_mode(
        input   clk,
        input   reset_n,        // asychronous negative reset
        input   p, r,
        output  m
);
        localparam S0 = 1'b0,
                   S1 = 1'b1;
                   
        logic      state_curr, state_next;
        // state register
        always_ff @ (posedge clk or negedge reset_n)begin
	        if(~reset_n) begin
		        state_curr < = S0;
		    end else begin
			    state_curr < = state_next;
			end
		end
        // next state logic
		always_comb begin
	        case (state_curr)
		        S0: state_next = (p) ? S1: S0;
		        S1: state_next = (r) ? S0: S1;
		        default: state_next = S0;
		    endcase
		end
        // output logic
        assign m = state_curr;
        // synthesis translate_off
        logic [2*8-1:0] state_dbg;
        always_comb begin
            case (state_curr)
                S0: state_dbg = "S0";
                S1: state_dbg = "S1";
            endcase
        end
        // synthesis translate_on
endmodule

module fsm_light(
        input   clk,
        input   reset_n,        // asychronous negative reset
        input   m,
        input   ta, tb,
        output  [1:0]   la, lb
);
        logic   [1:0]   la, lb;

        localparam S0 = 2'b00,
                   S1 = 2'b01,
                   S2 = 2'b10,
                   S3 = 2'b11;

        localparam  GREEN = 2'b00,
                   YELLOW = 2'b01,
                      RED = 2'b10;
        logic [1:0] state_curr, state_next;
        // state register
        always_ff @ (posedge clk or negedge reset_n)begin
	        if(~reset_n) begin
		        state_curr < = S0;
		    end else begin
			    state_curr < = state_next;
			end
		end
        // next state logic
        always_comb begin
	        case (state_curr)
		        S0: state_next = (ta) ? S0: S1;
		        S1: state_next = S2;
		        S2: state_next = (m | tb) ? S2: S3;
		        S3: state_next = S0;
		        default: state_next = S0;
		    endcase
		end
        // output logic
        always_comb begin
	        case (state_curr)
			    S0: {la, lb} = {GREEN, RED};
			    S1: {la, lb} = {YELLOW, RED};
			    S2: {la, lb} = {RED, GREEN};
			    S3: {la, lb} = {RED, YELLOW};
			    default: {la, lb} = {GREEN, RED};
			endcase
		end
        // synthesis translate_off
        logic [2*8-1:0] state_dbg;
        always_comb begin
            case (state_curr)
                S0: state_dbg = "S0";
                S1: state_dbg = "S1";
                S2: state_dbg = "S2";
                S3: state_dbg = "S3";
            endcase
        end
        // synthesis translate_on
endmodule
```
![[Pasted image 20240603220114.png]]
___
