## NAME: JAYAGAR.T.
## REG NO: 24901219.
# EXPERIMENT - 6:IMPLEMENTATION OF SERIAL IN SERIAL OUT SHIFTREGISTER.

# AIM:

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

# SOFTWARE REQUIRED:

Quartus prime

# THEORY:
A Serial-In Serial-Out (SISO) shift register is a sequential logic circuit used for temporary data
storage and transfer. It shifts binary data serially, one bit at a time, through a series of flip-flops
connected in sequence. Each flip-flop represents one bit of storage, and the number of flip-flops
determines the register's capacity.
The SISO operation begins with a clock signal synchronizing data movement. On each clock pulse,
the input bit is fed into the first flip-flop, and the existing bits are shifted one position towards the
output. This continues until the data is completely transferred or shifted out.
SISO shift registers are commonly used in data serialization, where parallel data is converted into a
serial stream for transmission, or in time-delay circuits. They offer simplicity in design but are slower
compared to parallel methods, as data transfer requires multiple clock cycles
# SISO shift Register:

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

# Procedure:
1.Launch Quartus on your computer and create a new project: Go to File → New Project Wizard.
Specify the project name, directory, and top-level entity name (e.g., SISO shift register).
Create the JK Flip-Flop Circuit and implement the SISO shift register by writing VHDL/Verilog code.
Go to File → New → Select Verilog File.
Compile the Project Click on Processing → Start Compilation.
Fix any syntax or schematic errors if present.
Simulate the Circuit: Go to Tools → University Program VWF.
Define the inputs for SI,SO and CLK in the waveform editor.
Run the simulation and observe the waveforms.
Verify the Results. Compare the simulated results with the truth table for a SISO shift register.



# PROGRAM:
```
module SISO(clk, sin, q);
input clk;
input sin;
output reg[3:0] q;
always @(posedge clk)
begin
q[0] <= sin;
q[1] <= q[0];
q[2] <= q[1];
q[3] <= q[2];
end
endmodule
```

# RTL OUTPUT:
![WhatsApp Image 2024-12-12 at 17 21 26_65a09ed4](https://github.com/user-attachments/assets/021f9d7f-9131-4220-808f-871ce78dc326)


# OUTPUT WAVEFORM:
![WhatsApp Image 2024-12-12 at 17 22 09_67984b3b](https://github.com/user-attachments/assets/2fcfd835-e841-41b9-9790-b73fde0e4ec1)

# RESULTS:
Thus SISO Shift Register is implemented using verilog and validated using their waveform and verified successfully.
