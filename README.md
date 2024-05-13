# EXP.NO:04
# DATE  :01/04/2024

# SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

**AIM:**

 To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using vivado 2023.1.

**APPARATUS REQUIRED:**

Vivado 2023.1

**PROCEDURE:**

1. Open Vivado: Launch Xilinx Vivado software on your computer.

2. Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3. Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4. Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5. Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6. Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7. Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8. Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9. View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.


**LOGIC DIAGRAM**

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

# CODE
```


module srff(s,r,clk,reset,q);
input s,r,clk,reset;
output reg q;
always@(posedge clk)
begin
if(reset==1)
q =1'b0;
else 
begin
case({s,r})
 2'b00: q = q;
 2'b01: q = 1'b0;
 2'b10: q = 1'b1;
 2'b11: q = 1'bx;
 default:q = ~q;
endcase
end 
end
endmodule

```
# OUTPUT

![324166487-dfe87063-e285-4985-b482-9637df3ae56d](https://github.com/KarthikeyanManickam/VLSI-LAB-EXP-4/assets/164841362/7883d11c-711a-40cb-9fe7-e5239d01e90d)

JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

# CODE
```


module jk_ff(j,k,clk,reset,q);
input j,k,clk,reset;
output reg q;
always@(posedge clk)
begin
if(reset==1)
q =1'b0;
else 
begin
case({j,k})
 2'b00: q = q;
 2'b01: q = 1'b0;
 2'b10: q = 1'b1;
 2'b11: q = ~q;
 default:q =1'b0;
endcase
end 
end
endmodule
```
# OUTPUT

![324166554-754d6a7b-3888-4fb7-acf0-ae0680dfa1f2](https://github.com/KarthikeyanManickam/VLSI-LAB-EXP-4/assets/164841362/b9724b69-297c-4d5c-a2e2-567a0548245a)

T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)

# CODE
```


module tff(clk,rst,j,q);
input clk,rst,j;
output reg q;
always@(posedge clk)
begin
case(t)
1'b0:q=q;
1'b1:q=~q;
default=q=1'b0;
endcase
end
endmodule
```
# OUTPUT

![324166604-91412bd9-30d7-4c37-b6ed-64c61489f9b1](https://github.com/KarthikeyanManickam/VLSI-LAB-EXP-4/assets/164841362/9c571479-abde-46a7-b385-2021283c5fc7)


D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)

# CODE
```


module dff(clk,rst,d,q);
input clk,rst,d;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
q=d;
end
endmodule
```
# OUTPUT

![324166658-dd3396d0-affa-4f7f-aa6b-3ea824d7b564](https://github.com/KarthikeyanManickam/VLSI-LAB-EXP-4/assets/164841362/bfa6b09f-82b4-4389-b336-16796d39abd5)


COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)

# CODE
```


module updown(clk,rst,up_down,count);
input clk,rst,up_down;
output reg[3:0]count;
always@(posedge clk)
begin
if(rst==1)
count <= 4'b0000;
else if (up_down == 1'b1)
count <= count + 1'b1;
else
count <= count-1'b1;
end
endmodule
```
# OUTPUT

![324166810-08d84db9-7847-4a03-a915-1fad58ce7f0f](https://github.com/KarthikeyanManickam/VLSI-LAB-EXP-4/assets/164841362/e206c68e-7bb4-4e80-8f47-f9a4c5e0bd70)


  


RESULT

 Thus simulation and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using vivado 2023.1 is verified successfully.

