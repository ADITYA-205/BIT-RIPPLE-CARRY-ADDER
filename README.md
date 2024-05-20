## 4 BIT RIPPLE CARRY ADDER
### DEVELOPED BY: S ADITYA
### REG NO:212223040007
### Program :
```
module ripple_carry_adder_4bit (
    input [3:0] a, b,
    input cin,
    output [3:0] sum,
    output cout
);
    wire c1, c2, c3;

    full_adder fa0 (.a(a[0]), .b(b[0]), .cin(cin),  .sum(sum[0]), .cout(c1));
    full_adder fa1 (.a(a[1]), .b(b[1]), .cin(c1),   .sum(sum[1]), .cout(c2));
    full_adder fa2 (.a(a[2]), .b(b[2]), .cin(c2),   .sum(sum[2]), .cout(c3));
    full_adder fa3 (.a(a[3]), .b(b[3]), .cin(c3),   .sum(sum[3]), .cout(cout));
endmodule

Create a Testbench:

module testbench;
    reg [3:0] a, b;
    reg cin;
    wire [3:0] sum;
    wire cout;

    ripple_carry_adder_4bit rca (.a(a), .b(b), .cin(cin), .sum(sum), .cout(cout));

    initial begin
        // Apply test vectors
        a = 4'b0000; b = 4'b0000; cin = 0;
        #10;
        a = 4'b0001; b = 4'b0001; cin = 0;
        #10;
        a = 4'b0010; b = 4'b0010; cin = 1;
        #10;
        a = 4'b1111; b = 4'b1111; cin = 1;
        #10;
        $stop; // End simulation
    end
endmodule
```
## OUTPUT:
![image](https://github.com/ADITYA-205/BIT-RIPPLE-CARRY-ADDER/assets/169021938/f823005e-c59f-42e4-a30c-cd37007af758)



 
 
