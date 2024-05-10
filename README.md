# AIM: 
To simulate and synthesis 8bit synchronous up-down counter  using vivado. 
# APPARATUS REQUIRED: 
vivado 2023.2 software. 
# PROCEDURE: 
STEP:1 Start the vivado software, Select and Name the New project. 
STEP:2 Select the device family, device, package and speed. 
STEP:3 Select new source in the New Project and select Verilog Module as the 
Source type. 
STEP:4 Type the File Name and module name and Click Next and then finish 
button. Type the code and save it. 
STEP:5 Select the run simulation and then run Behavioral Simulation in the 
Source Window and click the check syntax. 
STEP:6 Click the simulation to simulate the program and give the inputs and 
verify the outputs as per the truth table. 
STEP:7 compare the output with truth table.# 8BIT_SYNCHRONOUS_UP-DOWN_COUNTER
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/e1af47bf-e77f-446e-9fe0-e0ca3d1a7cfd)
# Here is a diagram showing the circuit in the "up" counting mode
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/8a6dd34b-5226-4d93-9bff-d87ab85aeabc)
# Here, shown in the "down" counting mode
![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/9a30ebd6-6692-48d0-b64b-41b896d6de4a)
# verilog code
module up_down_counter (
    input wire clk,       // Clock input
    input wire rst,       // Reset input
    input wire up_down,   // Up/Down control input
    output reg [7:0] out  // 8-bit counter output
);

// Initial value for the counter
reg [7:0] counter = 8'b00000000;

// Synchronous counter logic
always @(posedge clk or posedge rst) begin
    if (rst)                // Reset condition
        counter <= 8'b00000000;
    else if (up_down)       // Up count condition
        counter <= counter + 1;
    else                    // Down count condition
        counter <= counter - 1;
end

// Output assignment
assign out = counter;

endmodule
# output
![8bitupdown](https://github.com/lathika024/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/165888553/af03e678-7715-4ade-b2ef-a9465fd865fe)


# result
thus the 8bit synchronous up-down counter has been verified successfully
