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


Step 1:  Type the program in Quartus software.

Step 2:  Compile and run the program.

Step 3:  Generate the RTL schematic and save the logic diagram.

Step 4:  Create nodes for inputs and outputs to generate the timing diagram.

Step 5:  For different input combinations generate the timing diagram.


**PROGRAM**

~~~
module synchronous_up_counter (
    input clk,       // Clock input
    input reset,     // Active-high synchronous reset
    output reg [3:0] q  // 4-bit counter output
);

// Counter Logic
always @(posedge clk) begin
    if (reset)       // If reset is high, reset counter to 0
        q <= 4'b0000;
    else
        q <= q + 1;  // Increment counter
end

endmodule

~~~


Developed by: Santhose Arockiaraj J

RegisterNumber:24900171


**RTL LOGIC UP COUNTER**

![Screenshot 2024-12-17 112558](https://github.com/user-attachments/assets/f4f0a1d5-81ed-4c51-ab35-a25d2493f1a4)

**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot 2024-12-17 112710](https://github.com/user-attachments/assets/07b12b98-605c-4959-9070-2b74f15e74e6)

**TRUTH TABLE**

![Screenshot 2024-12-17 112856](https://github.com/user-attachments/assets/a3911da6-6e0d-4dd1-bf5e-b47726d6b496)

**RESULTS**

Thus,4 bit synchronous up counter and validate functionality is verified.
