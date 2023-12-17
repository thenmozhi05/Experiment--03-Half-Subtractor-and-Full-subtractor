## Developed by: THENMOZHI P
## RegisterNumber:  23005024
## Experiment 03 Half Subtractor and Full subtractor
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![Screenshot 2023-12-11 185045](https://github.com/mounika2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145633112/e7b5a0d5-3416-4d90-bf7a-da2d5117509c)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![Screenshot 2023-12-11 185115](https://github.com/mounika2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145633112/a6cd7daf-744a-41ec-bf31-b7836c3c9e35)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure

1.Use module projname(input,output) to start the Verilog programmming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.Use each output to represnt onre for differnce and the other for borrow.

5.End the verilog program using keyword endmodule


## Program:
## HALF SUBTRACTOR

module hs(a,b,borrow,diff);
input a,b;
output diff,borrow;
assign diff=a^b;
assign borrow=~a&b;
endmodule

## FULL SUBTRACTOR

module hs(a,b,bin,borrow,diff);
input a,b,bin;
output diff,borrow;
assign diff=(a^b)^bin;
assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
endmodule

### Truthtable
# Half Subtractor
![Screenshot 2023-12-11 185346](https://github.com/mounika2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145633112/7f28de09-71d5-4288-9bbb-0f0a4a032ba3)
# Full Subtractor
![Screenshot 2023-12-11 185438](https://github.com/mounika2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145633112/a79550a3-8864-4e2f-b255-476a67bf7aaa)

###  RTL realization
# Half subtractor
![Screenshot 2023-12-11 185516](https://github.com/mounika2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145633112/4222ecd0-f2bc-4aab-ad2d-d050cb75daab)
# Full subtractor
![Screenshot 2023-12-11 185525](https://github.com/mounika2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145633112/e1752a58-46f3-4df2-af5f-01002261a62b)


### Timing diagram 
# Half subtractor
![Screenshot 2023-12-11 185622](https://github.com/mounika2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145633112/b697b725-5320-4ee5-ba56-c49ba423bdc5)
# Full subtractor
![Screenshot 2023-12-11 185722](https://github.com/mounika2005/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/145633112/25b35abf-266f-4a35-83ed-11485b40217d)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
