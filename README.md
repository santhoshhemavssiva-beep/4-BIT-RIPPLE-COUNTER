# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

 Developed by:SANTHOSH SIVAKUMAR
 RegisterNumber:212225040382
~~~
module Exp7(q, clk, reset);

output [3:0] q;
input clk, reset;

T_FF tff0(q[0], clk, reset);
T_FF tff1(q[1], q[0], reset);
T_FF tff2(q[2], q[1], reset);
T_FF tff3(q[3], q[2], reset);

endmodule


module T_FF(q, clk, reset);

output q;
input clk, reset;

wire d;

D_FF dff0(q, d, clk, reset);

not n1(d, q);

endmodule


module D_FF(q, d, clk, reset);

output q;
input d, clk, reset;

reg q;

always @(negedge clk or posedge reset)
begin
   if (reset)
       q = 1'b0;
   else
       q = d;
end

endmodule
~~~
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="1481" height="869" alt="646929083-7d1fb700-02fe-4c83-a6f6-d95c9f069261" src="https://github.com/user-attachments/assets/741d53c3-4d60-4cce-aca6-098d8c4c1fe4" />

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="1484" height="867" alt="646929231-ec11a6c0-b515-41bc-a586-181fa24c3225" src="https://github.com/user-attachments/assets/d15101d4-10e6-4a17-8cef-add99083aee1" />

**RESULTS**The 4-bit Ripple Counter was successfully designed and its counting operation was verified.
