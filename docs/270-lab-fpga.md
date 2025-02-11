# Using the 270 lab FPGAs

In the 270 lab (BHEE 164), the FPGAs can be used for implementing simple designs.

1. Log in on the ecn (Linux) machine at a lab station.

2. Open the terminal and run `~ece270/bin/setup`

3. To use your SystemVerilog design with the FPGA, it will be necessary to use a top module wrapper to connect the ports of your design to the ports of the FPGA. 

4. Create a top module called `top.sv` in the same directory as the rest of your design.

5. The top module I/O should be copied as follows:
```
module top (
	// I/O ports
	input  logic hz100, reset, //sys clk @ 100 Hz
	input  logic [20:0] pb,
	output logic [7:0] left, right,
				 ss7, ss6, ss5, ss4, ss3, ss2, ss1, ss0,
	output logic red, green, blue,
		// UART ports
	output logic [7:0] txdata,
	input  logic [7:0] rxdata,
	output logic txclk, rxclk,
	input  logic txready, rxready
	);
	// Wire the FPGA ports to the ports of your design here:

endmodule
```

6. Within the top module, wire the FPGA ports to the ports of your design.

7. Copy the `Makefile` and the `pinmap.pcf` from `~/Desktop/ece270` into the directory that has your design.

8. In the Makefile, edit `TB =` to have the name the testbench you want to run. By default, the Makefile will run `tb.sv`

9. In the Makefile, edit `SRC =` to have the names of your source files, including `top.sv`, with spaces between each name.

9. In the same directory, run `make cram` to cram your source files onto the FPGA.

10. In the same directory, run `make verify` to run your testbench.