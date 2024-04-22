# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using vivado.

SOFTWARE REQUIRED: vivado 2023.2

PROCEDURE: 
1. Open Vivado: Launch Xilinx Vivado software on your computer.

2. Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

3. Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

4. Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

5. Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

6. Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

7. Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

8. Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

9. View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.

Logic Diagram :

Logic Gates:
# program
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
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)
# output
![WhatsApp Image 2024-04-22 at 11 38 23_3e9f1ee4](https://github.com/S-Mohankumar/VLSI-LAB-EXP-1/assets/163832108/ad9507f3-1c4f-4b6a-bc3d-67bf6a74f8ff)



Half Adder:
# program
```
module halfadder(a,b,sum,carry);
input a,b;
output sum,carry;
xor g1(sum,a,b);
and g2(carry,a,b);
endmodule
```


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)
# output
![WhatsApp Image 2024-04-22 at 11 38 50_2afc5abc](https://github.com/S-Mohankumar/VLSI-LAB-EXP-1/assets/163832108/efffc5bf-024d-467c-a88b-412b75c6b0c3)



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
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)
# output
![WhatsApp Image 2024-04-22 at 11 40 01_fb7c05c6](https://github.com/S-Mohankumar/VLSI-LAB-EXP-1/assets/163832108/884122a1-c694-40a9-8456-cb77a733d4d0)



Half Subtractor:
# program
```
module halfsubtractor(a,b,diff,borrow);
input a,b;
output diff,borrow;
xor g1(diff,a,b);
and g2(borrow,~a,b);
endmodule
```

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)
# output
![WhatsApp Image 2024-04-22 at 11 39 15_5ca24d68](https://github.com/S-Mohankumar/VLSI-LAB-EXP-1/assets/163832108/4e2dcaa7-9ccb-4518-913b-381ecfa30ba1)




Full Subtractor:
# program
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

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)
# output
![WhatsApp Image 2024-04-22 at 11 40 30_edad6de6](https://github.com/S-Mohankumar/VLSI-LAB-EXP-1/assets/163832108/2b8e0dc7-d0d0-4fee-83a4-a83d802cb4ae)




8 Bit Ripple Carry Adder
# program
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


![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)
# output
![WhatsApp Image 2024-04-22 at 11 41 14_03b7bc27](https://github.com/S-Mohankumar/VLSI-LAB-EXP-1/assets/163832108/3de8411b-ffbe-470b-8658-7e5c6699a3d8)








RESULT:
Hence simulate and synthesis Logic Gates,Adders and Subtractor using vivado.

