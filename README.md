Name: A Ahil Santo

Register Number: 24900087

# EXP4: FULL ADDER AND SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![full-adder-circuit](https://github.com/user-attachments/assets/c690f0e1-8685-4ae4-9583-fd608860e6f1)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![fullsubtractorcircuit](https://github.com/user-attachments/assets/d95fff6a-22f3-47a1-828c-ee9bc3bd5926)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

**Procedure**

Write the detailed procedure here

**Program:**

*Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.*

**Full Adder**

```
module fadd(a,b,c,sum,carry);
input a,b,c;
output sum,carry;
wire w1,w2,w3;
assign sum=a^b^c;
assign w1=a&b;
assign w2=b&c;
assign w3=c&a;
assign carry=w1|w2|w3;
endmodule 
```

**Full Subtractor**

```
module fsub(a, b, bin, diff, borrow);
input a, b, bin;
output diff, borrow;
wire w1, w2, w3, w4;
xor g1(diff, a, b, bin);
not g2(w1, a);          
and g3(w2, w1, bin);    
and g4(w3, w1, b);     
and g5(w4, b, bin);     
or g6(borrow, w2, w3, w4); 
endmodule
```

**RTL Schematic**

**Full Adder**

![hulladder rtl circuit](https://github.com/user-attachments/assets/9ec03764-44ef-4e18-a3b6-062f20eb750d)

**Full Subtractor**

![fsub rtl](https://github.com/user-attachments/assets/794900d8-f661-410a-8ea9-59061ad92f40)

**Output Timing Waveform**

**Full Adder**

![Screenshot (13)](https://github.com/user-attachments/assets/f5bc93f4-4436-44ad-ba09-69ef713dcbd2)

**Full Subtractor**

![Screenshot (23)](https://github.com/user-attachments/assets/e4794ca8-3d03-4b36-a635-29e1bb389293)

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



