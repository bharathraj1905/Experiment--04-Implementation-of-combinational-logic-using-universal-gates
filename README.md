# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Procedure
```
The input and output variables are allocated with letter symbols. The exact truth table that defines the required relationships between inputs and outputs is derived. The simplified Boolean function is obtained from each output. The logic diagram is drawn.
```
## Program:
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
```
Developed by: b.barathraj
RegisterNumber: 212222230019
```
## F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
```
module f1(A,B,C,D,F1);
input A,B,C,D;
output F1;
wire p,q,r,s,t;
assign p = (~A & ~B & ~C & ~D);
assign q = (A & ~C & ~D);
assign r = (~B & C & ~D);
assign s = (~A & B & C & D);
assign t = (B & ~C & D);
assign F1 = p | q | r | s | t;
endmodule
```
## F2=xy’z+x’y’z+w’xy+wx’y+wxy
```
module imp(w,x,y,z,F2);
input w,x,y,z;
output F2;
wire p,q,r,s,t;
assign p= (x & ~y & z);
assign q= (~x & ~y & z);
assign r= (~w & x & y);
assign s= (w & ~x & y);
assign t= (w & x & y);
assign F2= p | q | r | s | t;
endmodule
```
## RTL
## F1:

![rtl ex  2 1](https://github.com/bharathraj1905/Experiment--04-Implementation-of-combinational-logic-using-universal-gates/assets/121490575/6f751620-4fed-4a39-8b8f-345185bdeae8)


## F2:
![rtl exp 2 2](https://github.com/bharathraj1905/Experiment--04-Implementation-of-combinational-logic-using-universal-gates/assets/121490575/e1ae3bf0-c5fe-4bfc-bb4c-c2f9299ea85a)


## Timing Diagram
## F1:

![time diagram exp 2 1](https://github.com/bharathraj1905/Experiment--04-Implementation-of-combinational-logic-using-universal-gates/assets/121490575/4cb041af-7c1e-40c8-abd9-19aa2be6b3b5)


## F2:
![time diagram exp 2 2](https://github.com/bharathraj1905/Experiment--04-Implementation-of-combinational-logic-using-universal-gates/assets/121490575/5227b392-751d-4445-9cfb-c3dcb0673722)


## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
