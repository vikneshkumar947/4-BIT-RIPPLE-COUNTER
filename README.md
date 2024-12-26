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
```
module e12(
   input wire clk,  
   output reg [3:0] count
);


always @(posedge clk) begin
   if (count == 4'b1111) 
       count <= 4'b0000;
   else
       count <= count + 1; 
end

endmodule


module RippleCounter_tb;


reg clk;


wire [3:0] count;


RippleCounter uut(
   .clk(clk),
   .count(count)
);

initial begin
   clk = 0;
   forever #5 clk = ~clk; 
end


initial begin
   
   #10;
   

   $display("Time | Count");
   $display("-----------------");
   
 
   repeat (16) begin
       #5; 
       $display("%4d | %b", $time, count);
   end
   
   $finish;
end

endmodule
```
 Developed by:S.Viknesh kumar RegisterNumber:24008610
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/49cbfa19-3de7-40b1-ad14-bc6a62f680d4)

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/a64fed41-95d9-46a2-93e0-acf5c1a6cbd9)

**RESULTS**
Thus the outputs of 4 Bit Ripple Counter are verified by synthesizing and simulating the Verilog code
