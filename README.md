### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

/* write all the steps invloved */

**PROGRAM**
```
module upcount(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: Mohamed Hafees R
RegisterNumber:25004079
*/

**RTL LOGIC UP COUNTER**

<img width="592" height="209" alt="image" src="https://github.com/user-attachments/assets/fac9c70a-5e16-4c09-ac37-846d07176f79" />


**TIMING DIAGRAM FOR IP COUNTER**

<img width="834" height="211" alt="328020802-3d3ee8ff-26c0-43d0-ab37-ab10982fd5f6" src="https://github.com/user-attachments/assets/f0373cba-4f22-4acf-a055-6064c7ee6650" />


**TRUTH TABLE**

![WhatsApp Image 2025-12-10 at 11 23 13_273ebd5e](https://github.com/user-attachments/assets/90523dc2-e78f-41e0-9b05-3fecff7a83a0)

**RESULTS**
