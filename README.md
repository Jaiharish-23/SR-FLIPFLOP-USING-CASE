# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

Step 1: Open Quartus II in your laptop.

Step 2: Write code to implement SR flipflop using Verilog and validating their functionality using their functional tables.

Step 3: Run compilation to check for errors.

Step 4: Open waveform output and load input values.

Step 5: Run simulation to get the output.

Step 6: Open in RTL viewers to get RTL diagram output.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
Developed by: Jai harish.R 
RegisterNumber: 24006817
*/
```
module SR_FLIP_FLOP(s, r, clk, rst, q, qbar); 
    input s; 
    input r; 
    input clk; 
    input rst; 
    output q; 
    output qbar; 
reg q,qbar; 
always @ (posedge(clk) or posedge(rst)) begin 
if(rst==1'b1) begin 
q= 1'b0;qbar= 1'b1;
 end 
  else if(s==1'b0 && r==1'b0) 
   begin 
  q=q; qbar=qbar; 
  end 
   else if(s==1'b0 && r==1'b1) 
    begin 
  q= 1'b0; qbar= 1'b1; 
  end 
    else if(s==1'b1 && r==1'b0) 
    begin 
  q= 1'b1; qbar= 1'b0; 
  end 
  else  
  begin 
  q=1'bx;qbar=1'bx; 
  end 
  end 
endmodule
```
**RTL LOGIC FOR FLIPFLOPS**

![{7243C3D5-6F34-469F-92F1-46A8A9602355}](https://github.com/user-attachments/assets/f3c7ec55-189f-4908-a94d-fc03bcdcac45)



**TIMING DIGRAMS FOR FLIP FLOPS**
![Screenshot (250)](https://github.com/user-attachments/assets/668106a7-08a9-4a3a-8928-0596bcf0eb26)

**RESULTS**

