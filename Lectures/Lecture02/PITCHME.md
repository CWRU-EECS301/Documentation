#HSLIDE

## Hardware Description Language

* Programmatically describe digital logic circuits
* Differences from other programming languages
	* Concurrent processes
	* Notion of time (required for simulation)
	* Emphasis on simulation
* Two major HDLs for FPGAs: **Verilog** and **VHDL**


#HSLIDE

## VHDL

* Developed by request of the Dept. of Defense in the late 1980s
* VHSIC HDL (Very High Speed Integrated Circuit Hardware Description Language)
* Based on ADA (which was also developed by DoD)
* Standardized in 1987 as IEEE 1076
* Quartus defaults to the VHDL 1993 standard

#HSLIDE

## Verilog

* Originally developed by **Gateway Design Automation** in the early 1980s
* Popularized by **Cadence Design Systems** for logic simulation
* Many features borrowed from the C language
* Standardized in 1995 as IEEE 1364
* Quartus defaults to the Verilog-2001 standard

#HSLIDE

## SystemVerilog

* Superset of the Verilog-2005 standard
* Added modern language features
* Comparing SystemVerilog to Verilog is like comparing C++ to C
* Vendor support is stablizing

#HSLIDE

## RTL Logic (Register Transfer Level Logic)

![RTL Logic](https://raw.githubusercontent.com/CWRU-EECS301/Documentation/master/Lectures/Lecture02/rtl-logic.png)

* HDL behavioral models are translated to RTL logic
* RTL logic is synthesized into Gate-level logic
* Gate-level logic is mapped to the FPGA cell structure

#HSLIDE

## FPGA Structure (Altera Cyclone V)

![Cyclone V Floorplan](https://raw.githubusercontent.com/CWRU-EECS301/Documentation/master/Lectures/Lecture02/cv_floorplan.gif)

* FPGA fabric consists mainly of ALMs (or CLBs on Xilinx FPGAs)
* Other Hard-IP features are added for additional capabilities

#HSLIDE

## ALM (Adaptive Logic Module)

* Cyclone V 5CSEA5 FPGA has 32,075 ALMs

![Cyclone V ALM](https://raw.githubusercontent.com/CWRU-EECS301/Documentation/master/Lectures/Lecture02/cv_alm01.png)

#HSLIDE

## Verilog vs VHDL

* Both languages are designed to solve the same problem
* Both have similar structures to accomplish the same tasks
* Syntax is the biggest difference
	* VHDL is not case-sensitive, whereas Verilog is
	* VHDL has stronger type checking than Verilog
	* Verilog is more flexible for generating simulation models
	* Verilog is more succinct, whereas VHDL is verbose

#HSLIDE

## Verilog Module

```
module Example_Logic_Block
(
    input a, b, c;
    output z;
);

	assign z = (a & b) ^ c;  

endmodule
```

#HSLIDE

## VHDL Enity/Architecture

```
library ieee;
use ieee.std_logic_1164.all;

entity Example_Logic_Block is
port
(
	a, b, c : in std_logic;
	z : out std_logic;
);
end entity;

architecture rtl of Example_Logic_Block is
begin

	z <= (a and b) xor c;
	
end rtl;
```

#HSLIDE

## Signal Assignments

### Verilog

```
wire a, b, c; // Defined anywhere in module (above usage)

assign c = (a & ~b) | (~a & b);
```

### VHDL

```
signal a, b, c: std_logic; -- Defined in 

begin
	c <= (a and not b) or (not a and b);
end
```
