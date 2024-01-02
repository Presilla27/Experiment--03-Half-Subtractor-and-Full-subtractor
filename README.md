# Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime

## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

##procedure


1.Use module projname(input,output) to start the Verilog programmming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.Use each output to represnt onre for differnce and the other for borrow.

5.End the verilog program using keyword endmodule


## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.

![image](https://github.com/Presilla27/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155127632/ab63394b-b4e6-4a6a-ad9c-8081aa17ca9f)




Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

##program

module project_4_1(a,b,borrow,diff);
input a,b;
output borrow,diff;
assign borrow=~a&b;
assign diff=a^b;
endmodule


##Truthtable

![image](https://github.com/Presilla27/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155127632/eaa1eb80-f8dd-4f5b-8470-1fa1f1ab4819)

##RTL realization


![image](https://github.com/Presilla27/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155127632/0c290802-7348-4ee4-bfa6-4a90f5a87ad4)


##Timing diagram


![image](https://github.com/Presilla27/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155127632/d2c6dd66-b0b4-4705-89b4-c3064296eeb5)




## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 


![image](https://github.com/Presilla27/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155127632/951eeafc-6de5-4afc-b28e-08a7c5c79d01)



Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

Program:
module project_4_2(a,b,bin,borrow,diff);
input a,b,bin;
output diff,borrow;
assign diff=(a^b)^bin;
assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
endmodule



##Truthtable


![image](https://github.com/Presilla27/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155127632/d3faa789-a2ae-46ce-8c1c-3e74e3eb9396)


##RTL realization


![image](https://github.com/Presilla27/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155127632/2d2d52a6-7277-4336-8bb0-b6c8a89d2b3a)


##Timing diagram


![image](https://github.com/Presilla27/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/155127632/52ce0b54-f500-452a-a945-e16e134e3606)



## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
