#HSLIDE


## Lab 3 Review

#HSLIDE

* **Logical Operators**
	* Used with boolean values
	
* **Bit-wise Operators**
	* Used with binary values
	
		
#HSLIDE

## Logic Operators

| Operation | Syntax |
|:---------:|:------:|
| Equal     | a == b   |
| Not Equal | a != b   |
| And       | a && b   |
| Or        | a &#124;&#124; b   |
| Not       | !a    |

#HSLIDE

## Bit-wise Operators

| Operation | Syntax |
|:---------:|:------:|
| NOT       | ~a    |
| AND       | a & b    |
| OR        | a &#124; b    |
| XOR       | a ^ b    |


#HSLIDE

## Logical Operatior Usage

```Verilog
wire event;
wire [3:0] condition;

if ( (event == 1'b1) && (condition != 4'h7) )
	State <= S1;
```

#HSLIDE

## Implied Boolean Value

```Verilog
wire event;

if (event)
	State <= S1;
```

Transitions when event == 1'b1

#HSLIDE

## Vector Boolean Values

| Vector  | Boolean Value |
|:-------:|:-------------:|
| 4'h0000 |    False      |
| 4'h0001 |    True       |
| 4'h1010 |    True       |
| 4'h1111 |    True       |


#HSLIDE

## Bit-wise Operator Usage

```Verilog
wire [3:0] a = 4'b1010;
wire [3:0] b = 4'b1011;
wire [3:0] c;

assign c = a & b;  // Result: 4'b1010;
assign c = a | b;  // Result: 4'b1011;
assign c = a ^ b;  // Result: 4'b0001;
assign c = ~a & b; // Result: 4'b0001;
```

#HSLIDE

## Bit-wise Reduction Operations

```Verilog
wire [3:0] a = 4'b0110;
wire b, c;

// AND all bits of 'a' together
assign b = &a; // Result: 1'b0

// Equivalent to:
assign c = a[3] & a[2] & a[1] & a[0];
```

#HSLIDE

## Bit-wise Reduction Operators

| Operation | Syntax |
|:---------:|:------:|
| AND       | &a    |
| OR        | &#124;a   |
| XOR       | ^a    |
| NAND      | ~&a   |
| NOR       | ~&#124;a   |
| NXOR      | ~^a   |

#HSLIDE

## Bit-wise NOT

* Looks like a reduction operator but is not

```Verilog
wire [3:0] a = 4'b1010;
wire [3:0] b;

assign b = ~a; // Result: 4'b0101

// Equivalent to:
assign b = { ~a[3], ~a[2], ~a[1], ~a[0] };
```


#HSLIDE

* `if()` statements allow bit-wise operators to be used as logical operators

```Verilog
wire [3:0] events;

if (events)
	State <= S1;
```

When `events == 4'h0000` statement is False, any other setting is True.

#HSLIDE

## Lab 4 Demostration

#HSLIDE

## I<sup>2</sup>C Bus Overview

#HSLIDE



