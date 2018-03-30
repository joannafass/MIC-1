<p align="center"> <b> ***MIC-1 (32-bit Computer)*** </b> </p>

**Creators: Philip Butts, Joanna Fass, Devin Smaldore**  
*Class: Assembly Language and Architecture*

This simulator is based on the architecture described in chapter 4 of **Structured Computer Organization (6th Edition)** by Andrew S. Tanenbaum. 

The example RAM/ROM modules that are provided will add hex values 8 and 42 and return 4a (74 in decimal).

How to run the machine:

   * Download and install Logisim from: <http://www.cburch.com/logisim/download.html>  
   * Find a Microcode/Macrocode Compiler such as [gmac](https://manned.org/gmac/40dd06bf "TkGate Microcode/Macrocode Compiler")
   
   1. Double click on the file Machine.circ - You should see an aerial view of the entire machine. Notice the list of circuits on the left.
   2. From the list, find and double click to view the RAM module. (*Use the hand pointer, not the mouse pointer*) Right click on the RAM component inside of that and load the image from the provided file named "RAM".
   3. Go back to the main circuit and select the desired simulation frequency from the simulate menu at the top.
   4. Make sure simulation is enabled
   5. Hit cmd+K , the program will be done once OP code FE is reached. Hit cmd+K to stop the simulation.

Notes:
The current RAM file is preloaded with 8 and 42 at word address 11 and 12, when the program ends, there should be a 4a at word address 13.

To change these numbers, hit cmd+K to stop the ticking, hit cmd+R to reset the simulation, reload the RAM from the original RAM file, right click on the RAM and select edit content, place your desired numbers in positions 11 and 12 (replacing 8 and 42), close the edit window, choose your desired module to view and hit cmd+k to run.

If you need to reload the Control Store ROM modules, load images named LEFT/RIGHT-ROM into appropriate module. Resetting the machine should not require a new reload. If you want to step through the instructions one at a time hit cmd+T.  

If you would like to view the source code for the IJVM micro and macro instructions, find the file mic_mac.gm and open in a text editor. In order to compile the file into Byte code, use the command:  
	
	gmac mic_mac.gm -o memory  
  
and reload the ROM and RAM modules from the memory file. It is important to note that the bytes for the RAM must be manually 0 padded.
Also, seperate the ROM left and right input from the memory file. Use the preloaded files as a template.
