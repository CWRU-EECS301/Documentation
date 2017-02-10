#HSLIDE

## LAB 2 REVIEW


#HSLIDE

```Verilog
parameter CLK_RATE = 50 // MHz
parameter DELAY_TIME = 1000; // nS

localparam DELAY_TICKS = DELAY_TIME / (1000.0 / CLK_RATE);
localparam COUNT_WIDTH = bit_index(DELAY_TICKS);
localparam ROLLOVER_VAL = { 1'b1, {(CNT_WIDTH){1'b0}} };
localparam COUNT_LOADVAL = ROLLOVER_VAL - DELAY_TICKS + 1'b1;

reg  [COUNT_WIDTH:0] count_reg; // Register size: COUNT_WIDTH + 1
wire   clock_tick;

assign clock_tick = counter[8]; // Rollover bit

always @(posedge CLK)
begin
	if (clock_tick)   // Reset the counter when clock_tick asserts
		counter <= COUNT_LOADVAL;  // Set the Load Value 
	else
		counter <= counter + 1'b1; // Increment the counter
end
```

#HSLIDE

```
reg [2:0] mux_sel_reg;

always @(posedge CLK)
begin
	if (SEL_NEXT)
		mux_sel_reg <= mux_sel_reg + 1'b1;
end

always @(posedge CLK)
begin
	case (mux_sel_reg)
		3'h0 : MUX_OUT <= 2'h0;
		3'h1 : MUX_OUT <= 2'h1;
		3'h2 : MUX_OUT <= 2'h2;
		3'h3 : MUX_OUT <= 2'h3;
		3'h4 : MUX_OUT <= 2'h3;
		3'h5 : MUX_OUT <= 2'h2;
		3'h6 : MUX_OUT <= 2'h1;
		3'h7 : MUX_OUT <= 2'h0;
	endcase
end
```

#HSLIDE

## LAB 3 OVERVIEW


#HSLIDE



