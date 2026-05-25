# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

/* write all the steps invloved */
1.Open Quartus Prime software and create a new project.
2.Select the appropriate device and create a new Verilog HDL file.
3.Write the Verilog program for JK Flip-Flop using if-else statements.
4.Save the file with the appropriate module name and compile the design.
5.Fix any syntax or compilation errors if present.
6.Generate the RTL schematic and verify the logic design.
7.Create the waveform input file and apply different combinations of J, K, and Clock inputs.
8.Run functional simulation and observe the output waveform.
9.Verify the obtained output with the JK Flip-Flop truth table.
10.Record the RTL diagram and timing diagram results.
**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by:SANJAY A
RegisterNumber:212225040367
*/
```
module deexp4(
input clk,
input j,
input k,
output reg q,
output reg qbar
);

always @(posedge clk) begin
if (j == 0 && k == 0) begin
    q <= q;
    qbar <= qbar;
end 
else if (j == 0 && k == 1) begin
    q <= 0;
    qbar <= 1;
end 
else if (j == 1 && k == 0) begin
    q <= 1;
    qbar <= 0;
end 
else if (j == 1 && k == 1) begin
    q <= ~q;
    qbar <= ~qbar;
end
end

endmodule
```
**RTL LOGIC FOR FLIPFLOPS**
<img width="958" height="453" alt="Screenshot 2026-05-25 200930" src="https://github.com/user-attachments/assets/b9d9d978-a434-410d-bcd9-64f0e7574f54" />

**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1058" height="590" alt="Screenshot 2026-05-25 200944" src="https://github.com/user-attachments/assets/a224fba6-6ad1-49fb-be01-01e2a8affaaf" />

**RESULTS**
Thus, the JK Flip-Flop using if-else statement was implemented successfully in Verilog using Quartus Prime and its functionality was verified using the functional (truth) table and timing waveform.
