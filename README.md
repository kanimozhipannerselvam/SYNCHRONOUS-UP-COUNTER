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
1.Initialize the shift register to a known state (e.g., all zeros). 

2.Input a bit serially into the shift register. 

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: kanimozhi
RegisterNumber: 212222230060
*/
```
module ex10(clk, sin, q);
input clk;
input sin;
output [3:0] q;
reg [3:0] q;
always @(posedge clk)
begin
q[0] <= sin;
q[1] <= q[0];
q[2] <= q[1];
q[3] <= q[2];
end
endmodule
```

**RTL LOGIC UP COUNTER**
![326267504-c449089a-1b48-4ae3-ae3d-2d4f03947342](https://github.com/kanimozhipannerselvam/SYNCHRONOUS-UP-COUNTER/assets/119476060/80fa392e-ca84-4eb1-96c1-205abb96f7ba)


**TIMING DIAGRAM FOR IP COUNTER**
![326267527-533092f8-05c2-4214-bf6a-c9a5d1a8e730](https://github.com/kanimozhipannerselvam/SYNCHRONOUS-UP-COUNTER/assets/119476060/2fe6fe03-b1d4-476b-98ec-69422c358cf0)



**TRUTH TABLE**

![326267546-1f6e1d9d-e49e-46af-8ff4-a6136db37b7d](https://github.com/kanimozhipannerselvam/SYNCHRONOUS-UP-COUNTER/assets/119476060/1311d8fa-8232-4599-b471-ed6fc43c9d63)


**RESULTS**
SISO Shift Register using verilog and validating their functionality using their functional tables has successful execution of the program.
