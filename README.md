# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :

Logic Gates:
# Program
```
module logicgate (a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;  
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b); 
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```
# output

![WhatsApp Image 2024-03-24 at 10 08 58_45ad85ba](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/fc73acb6-0a04-4925-b72f-4176be712215)

![WhatsApp Image 2024-03-24 at 10 09 14_1a613ed4](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/69bceb7f-666c-47ee-9cd6-c501e1f27366)

![WhatsApp Image 2024-03-24 at 10 09 26_7b822310](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/1a8f9950-5992-4a4e-a83e-a85de140288c)

![WhatsApp Image 2024-03-24 at 10 09 40_4e0ef419](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/a9797788-fd25-4240-a85c-14ecc3da3637)

![WhatsApp Image 2024-03-24 at 10 10 09_b90b7bc5](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/d452051e-8e60-4ef4-9318-51f7f7e23643)

![WhatsApp Image 2024-03-24 at 10 10 25_2e01c08e](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/8b0b7973-02b0-4689-847c-d3c72ed66bf8)

![WhatsApp Image 2024-03-24 at 10 11 11_8ca26556](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/477ecbcd-448b-443f-85b8-b3f7029385e0)







![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:
# Program
```
module halfadder(a,b,sum,carry);
input a,b;
output sum,carry;
xor g1(sum,a,b);
and g2(carry,a,b);
endmodule
```
# Output


![WhatsApp Image 2024-03-24 at 10 11 37_8ae7c791](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/412f046e-d516-4fbd-a1e5-afe9ccd7a75f)



![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:
# program
```
module fadd(a,b,c,sum,carry);
input a,b,c;
output sum,carry;
wire w1,w2,w3;
xor g1(w1,a,b);
and g2(w2,a,b);
xor g3(sum,w1,c);
and g4(w3,w1,c);
or g5(carry,w3,w2);
endmodule
```
# Output


![WhatsApp Image 2024-03-24 at 10 11 52_87c1f925](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/c2f09ccd-d79c-4d6d-b139-f333e099dd7c)



![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:
# Program
```
module halfsubtractor(a,b,diff,borrow);
input a,b;
output diff,borrow;
xor g1(diff,a,b);
and g2(borrow,~a,b);
endmodule
```
# Output



![WhatsApp Image 2024-03-24 at 10 12 06_40ea972e](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/0fc9a5e8-2b3d-444d-86a5-60f3b9da8f44)




Full Subtractor:
# Program
```
module fs(a,b,bin,d,bout);
input a,b,bin; 
output d,bout;
wire w1,w2,w3;
xor g1(w1,b,bin; 
xor g2(d,w1,a);
and g3(w2,a,~w1);
and g4(w3,~b,bin);
or g5(bout,w2,w3);
endmodule
```
# Output

![WhatsApp Image 2024-03-24 at 10 12 21_764cfe5f](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/076d50c1-4a7f-436c-9e16-14c10cbd1409)

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder
# Program
```
module ripplemod(a, b, cin, sum, cout);
input [07:0] a;
input [07:0] b;
input cin;
output [7:0]sum;
output cout;
wire[6:0] c;
fulladd a1(a[0],b[0],cin,sum[0],c[0]);
fulladd a2(a[1],b[1],c[0],sum[1],c[1]);
fulladd a3(a[2],b[2],c[1],sum[2],c[2]);
fulladd a4(a[3],b[3],c[2],sum[3],c[3]);
fulladd a5(a[4],b[4],c[3],sum[4],c[4]);
fulladd a6(a[5],b[5],c[4],sum[5],c[5]);
fulladd a7(a[6],b[6],c[5],sum[6],c[6]);
fulladd a8(a[7],b[7],c[6],sum[7],cout);
endmodule
module fulladd(a, b, cin, sum, cout);
input a;
input b;
input cin;
output sum;
output cout;
assign sum=(a^b^cin);
assign cout=((a&b)|(b&cin)|(a&cin));
endmodule
```
# Output

![WhatsApp Image 2024-03-24 at 10 12 49_bcfe74ff](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/163832108/b91c2a2c-c7ba-47a7-894b-5a5b35b3568f)


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:

----Type Verilog Code

OUTPUT:

-----Place a Waveform Generated from Xilinx ISE

RESULT:

