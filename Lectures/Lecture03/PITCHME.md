#HSLIDE

## DE1-SoC Board Hardware Programming Demo

* Refer to [Lab 2 Dev Kit Hardware Guide](https://github.com/CWRU-EECS301/Lab2-Assignment/blob/master/Lab2-Guide/Lab2-DevKitHardwareGuide.md)

#HSLIDE

# Verilog Overview


#HSLIDE

## Module

```Verilog
module Module_Name
#(
	// Parameter List
)
(
	// Port List
);

// Code Implementation

endmodule;
```

#HSLIDE

## Good Coding Practice

* One module definition per file
* Include comment header block for each module
	* Example: see any lab assignment module file
* Name of file should match name of module
* Prefix the filename of grouped modules
	* Example: `CLS_Scanner_Module.v`
	
#HSLIDE

## Parameters

* Similar concept to overloading in C++
* Parameters make module functionality flexible
* Simple parameters
	* Specify signal widths
	* Set delay parameters
* Complex parameters
	* Coupled with `generate` can completely change a module's function


#HSLIDE

## Parameter Example

```Verilog
parameter CLK_RATE = 50 // MHz
parameter DELAY_TIME = 1000; // nS
	
localparam DELAY_TICKS = DELAY_TIME / (1000.0 / CLK_RATE);
localparam COUNT_WIDTH = bit_index(DELAY_TICKS);
localparam COUNT_LOADVAL = {1'b1, {(CNT_WIDTH-1){1'b0}}, 1'b1} - DELAY_TICKS;

reg [COUNT_WIDTH:0] count_reg;
```


#HSLIDE

## Signal Types

* wire     (combinatorial signal)
* reg      (registered signal)
* integer  (unsigned integer, _usually_ 32-bit)
* real     (floating point, IEEE 64-bit)
* vectors (either wire or reg) are specified with [u:l]
	* `wire [7:0] bus_wire_of_8_bits`

#HSLIDE

## Numerical Constants

* Number constants specified in format: ```width'radix value```
* width is number of bits
* radix defines base of value
	* `h` for hexidecimal : `8'h3D`
	* `d` for decimal : `8'd61`
	* `o` for octal : `8'o055`
	* `b` for binary : `8'b00101101`


#HSLIDE

## Register

* `always` block with edge sensitive clock creates register

```Verilog
reg [15:0] data_reg;

always @(posedge CLK)
begin
	data_reg <= some_data;
end
```

#HSLIDE

## Shift Register

* Concatenation operator shifts the signal assignments
* Shift occurs when shift_data is asserted

```Verilog
reg [7:0] shift_reg;

always @(posedge CLK)
begin
	if (shift_data)
		shift_reg <= { shift_reg[6:0], shift_reg[7] };
end
```

#HSLIDE

## Multiplexer (non-registered)

* Continuous assignment using always block
* `mux` output selected by `mux_sel`

```Verilog
always @*
begin
	case (mux_sel)
		2'h0 : mux <= a;
		2'h1 : mux <= b;
		2'h2 : mux <= c;
		2'h3 : mux <= d;
	endcase
end
```

#HSLIDE

## Multiplexer (registered)

* Registered on rising-edge of clock

```Verilog
always @(posedge CLK)
begin
	case (mux_sel)
		2'h0 : mux <= a;
		2'h1 : mux <= b;
		2'h2 : mux <= c;
		2'h3 : mux <= d;
	endcase
end
```


#HSLIDE

## Rollover Counter

```Verilog
// Generate a clock tick every 100 clock cycles
reg [8:0] counter;
wire      clock_tick;

// Use counter rollover for clock tick
assign clock_tick = counter[8];

always @(posedge CLK)
begin
	if (counter[8])
		counter <= (9'h101 - 9'd100); // Reset the counter
	else
		counter <= counter + 1'b1; // Increment the counter
end
```

#HSLIDE

## Additional Reading

* [Lab 2 Component Reference](https://github.com/CWRU-EECS301/Lab2-Assignment/blob/master/Lab2-Project/Lab2-ComponentReference.md) document
