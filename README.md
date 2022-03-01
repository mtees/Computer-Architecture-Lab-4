# Computer-Architecture-Lab-4
module Lab4(A,B,Op,R);
    
    //declaring inputs and outputs
    input [7:0] A,B; // 8 bit inputs
    input [3:0] Op; // opcode
    output [7:0] R; //outputs
    wire [7:0] Reg1,Reg2;
    reg [7:0] Reg3;
    
    //Assigning A and B to perform operations
    assign Reg1 = A;
    assign Reg2 = B;
    //Assigning to output 
    assign R = Reg3;

    //operations based on opcode from input
    always @(Op or Reg1 or Reg2)
    begin
        case (Op)
		   4'b0000: // Addition
           Reg3 = Reg1 + Reg2 ;
			4'b0001: // xor 
           Reg3 = Reg1 ^ Reg2;
			4'b0010: // and 
           Reg3 = Reg1 & Reg2;
			4'b0011: // or
           Reg3 = Reg1 | Reg2;
			4'b0100: // nor
           Reg3 = ~(Reg1 | Reg2);
			4'b0101: // Logical shift right
           Reg3 = Reg1>>1;
			4'b0110: // Logical shift left
           Reg3 = Reg1<<1;
        endcase 
    end
    
endmodule
