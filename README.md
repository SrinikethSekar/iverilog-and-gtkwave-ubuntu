iVerilog and GTKWave

1.Installation:

In my laptop, I have "Ubuntu OS"{2024}, so I need to install everything via the
terminal. The main command for the installation is:

     sudo apt install iverilog gtkwave

After the installation, you will be able to use the platform.

2.How to Use:

Step 1: Write Verilog Code
First, write your Verilog code in any text editor and save it with the .v
extension (e.g., count.v). This is necessary for the conversion of the
Verilog code.

Step 2: Organize Files
After completing the coding and saving the file, allocate a separate
folder for the file. This makes accessing and managing it easier.

Step 3: Navigate to File Directory
Open the terminal and locate the directory where the file is saved. You
can navigate to the directory by using the cd command or drag and
drop the file into the terminal.

    cd (Path Directory of the file)

Step 4: Compile the Verilog Code
Use the iverilog command to compile your Verilog file:iverilog <file name>
Example:

    iverilog count.v
If there are any errors in the code, the terminal will indicate the errors
with the corresponding line numbers. This helps you debug effectively.

Step 5: Execute the Output File
After compilation, an output file (e.g., a.out) will be created in the
same folder. To execute the file, run the following command:

    vvp a.out
This will generate a new file in the folder with the .vcd extension
(e.g., dumpfile.vcd).
Note: If the .vcd file is not generated, it means the required
commands for GTKWave were not included in the Verilog
code.

Step 6: Add Testbench Code for GTKWave
To use GTKWave, you must include the following testbench syntax in
your Verilog code:

    initial begin
    $dumpfile("dumpfile.vcd");
    $dumpvars(0, Testbench);
    end
Use the above code in verilog. The $dumpfile directive specifies the .vcd file name, and
$dumpvars initializes the waveform variables for the testbench.

Step 7: Open the Waveform in GTKWave
Once the .vcd file is generated, open it using GTKWave:

    gtkwave dumpfile.vcd
GTKWave will launch, allowing you to analyze the input and output
waveforms. Verify the output using the testbench results.
