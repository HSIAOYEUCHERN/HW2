# HW2

![螢幕擷取畫面 2022-04-05 145315](https://user-images.githubusercontent.com/101077336/161696084-54de4e6e-6b79-464d-a901-4ded9819e687.png)

Blocking design:
```script=
module blocking(clk,rst_n,a_i,b_i,a_o,b_o);
input clk;
input rst_n;
input a_i, b_i;
output a_o, b_o;
  
reg a, b;
  
assign a_o = a;
assign b_o = b;
  
always @(posedge clk or negedge rst_n) begin
	if (~rst_n) begin
		a = a_i;
		b = b_i;
	end
	else begin
		a = b;
		b = a;
	end
end

endmodule
```
Blocking
![image](https://user-images.githubusercontent.com/101077336/166136209-a60f13a9-d294-402b-a2a8-873d8368d815.png)

nonBlocking
![image](https://user-images.githubusercontent.com/101077336/166136034-3359f4d8-8d79-47fb-bbcd-f345d73ae64f.png)
