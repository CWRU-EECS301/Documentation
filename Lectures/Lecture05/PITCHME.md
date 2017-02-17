#HSLIDE


##State Machine Overview

#HSLIDE

## State Encoding

* Binary
* Gray Code
* Hamming (Fault Tolerant)
* One-Hot

#HSLIDE

## Binary Encoding

* Simple Encoding to Minimize Registers

| State | Encoding |
|:-----:|:--------:|
|  S0   |    00    |
|  S1   |    01    |
|  S2   |    10    |
|  S3   |    11    |

#HSLIDE

## Gray Encoding

* One-bit Change Per Transition

| State | Encoding |
|:-----:|:--------:|
|  S0   |   00   |
|  S1   |   01   |
|  S2   |   11   |
|  S3   |   10   |

#HSLIDE

## One-Hot Encoding

* One Register Per State

| State | Encoding |
|:-----:|:--------:|
|  S0   |   0001   |
|  S1   |   0010   |
|  S2   |   0100   |
|  S3   |   1000   |

#HSLIDE

* **Combined Single Process** Vs **Split Two Process**
* Minimize State Usage
* All signals synchronous to single clock domain
* One State Machine per module
* 

#HSLIDE

## State Transitions & Actions

```Verilog
S0 :
begin
	// Entry Actions
	Action <= 1'b1;

	// State Transition
	if (Event)
		State <= S1;
end
```

#HSLIDE

### Never Read and Write In Same State

	```	
	S2 :
	begin
		counter <= counter + 1'b1;
	
		if (counter ==8'h73)
			State <= S3;
	end
	```

#HSLIDE



