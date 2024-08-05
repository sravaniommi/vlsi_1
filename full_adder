// 4bit fulladder
module fulladder ( input [3:0] a, b,  
                  input cin,  
                  output reg cout,  
                  output reg [3:0] sum);  
  
    always @ (a or b or cin) begin  
      {cout, sum} = a + b + cin;  
  end  
endmodule

//testBench

module test;
  reg[3:0] a,b;
  reg cin;
  wire[3:0] sum;
  wire cout;
  integer i;
  fulladder FA(a, b, cin, sum, cout);
  initial
    begin
      a<=0; b<=0; cin<=0;
      $dumpfile("dump.vcd");
      $dumpvars(0, test);
      $monitor($time, "a=%b,b=%b,cin=%b,sum=%b,cout=%b", a,b,cin,sum,cout);
      for (i=0; i<8; i++)
        begin
        #5  a=$random; b=$random; cin=$random;
        end
    end
endmodule
