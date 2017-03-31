#HSLIDE

## Vector Sections

* [ Upper : Lower ]
* [ Upper -: Width ]
* [ Lower +: Width ]

#HSLIDE

```Verilog
localparam A_WIDTH = 8;
localparam B_WIDTH = 5;

assign B0 = A[A_WIDTH-1 : A_WIDTH-B_WIDTH];
assign B1 = A[A_WIDTH-1 -: B_WIDTH];
assign B2 = A[A_WIDTH-B_WIDTH +: B_WIDTH];
```

#HSLIDE

![Vector Section](https://raw.githubusercontent.com/CWRU-EECS301/Documentation/master/Lectures/Lecture10/vector_sections_01.png)

#HSLIDE

![Vector Section](https://raw.githubusercontent.com/CWRU-EECS301/Documentation/master/Lectures/Lecture10/vector_sections_02.png)

#HSLIDE

![Vector Section](https://raw.githubusercontent.com/CWRU-EECS301/Documentation/master/Lectures/Lecture10/vector_sections_03.png)

#HSLIDE

![Vector Section](https://raw.githubusercontent.com/CWRU-EECS301/Documentation/master/Lectures/Lecture10/vector_sections_04.png)
