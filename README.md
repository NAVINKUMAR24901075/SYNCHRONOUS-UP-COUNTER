## NAME:S.NAVINKUMAR
## REG.NO:24901075
# EXPERIMENT-7: IMPLEMENTATION OF SYNCHRONOUS UP COUNTER

# AIM:

To implement 4 bit synchronous up counter and validate functionality.

# SOFTWARE REQUIRED:

Quartus prime

# THEORY:

A synchronous up counter is a type of sequential digital circuit that counts upward in a binary sequence, with all flip-flops triggered by a common clock signal. The key characteristic of a synchronous counter is that all flip-flops update their states simultaneously, ensuring precise and coordinated transitions, unlike asynchronous counters where flip-flops update one after another.

In a synchronous up counter, the number of flip-flops (𝑛n) needed is determined by the maximum count. The counter will count from 0 to 𝑁−1
N−1, where 𝑁N is the maximum value. To find the minimum number of flip-flops required, the formula 2𝑛≥𝑁2 n≥N is used.

Each flip-flop in the counter represents one bit of the binary output. The least significant bit (LSB) toggles with every clock pulse, while higher-order bits toggle based on the states of lower-order bits. Combinational logic, often implemented using AND, OR, or XOR gates, controls the inputs to the flip-flops to ensure the correct counting sequence.

Synchronous up counters are used in various applications, such as:
Event counting
Digital clocks
Frequency dividers
Addressing in memory systems

Their primary advantage is the uniform timing and faster operation due to the simultaneous updates of all flip-flops.

# 4 BIT SYNCHRONOUS UP COUNTER:

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

# PROCEDURE:

1.Launch Quartus on your computer and create a new project:
Go to File → New Project Wizard.

Specify the project name, directory, and top-level entity name.

Create the synchronous up counter and implement the synchronous up counter by writing VHDL/Verilog code.
Go to File → New → Select Verilog File.

Compile the Project
Click on Processing → Start Compilation.

Fix any syntax or schematic errors if present.

Simulate the Circuit:
Go to Tools → University Program VWF.

Define the inputs for CLK,out,rstn in the waveform editor.

Run the simulation and observe the waveforms.

Verify the Results.
Compare the simulated results with the truth table for a synchronous up counter.

# PROGRAM: 
~~~
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
~~~

# TRUTH TABLE:

![Screenshot 2024-12-23 104806](https://github.com/user-attachments/assets/9a3abc99-9c4d-4613-a4da-56c15dc061e3)

# RTL OUTPUT:

![Screenshot 2024-12-23 104221](https://github.com/user-attachments/assets/9e33df29-6fd0-4dff-81ee-8984dd051f5f)

# OUTPUT WAVEFORM:

![Screenshot 2024-12-23 104231](https://github.com/user-attachments/assets/73f07ff4-78b3-42f3-925a-9024ccedd733)

# RESULT:

Thus 4 bit synchronous up counter is implemented using verilog and validate using their waveform and verified successfully
