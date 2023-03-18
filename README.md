# Simple 8 Bit Computer

#### [Link To Video](https://www.youtube.com/watch?v=bzLV9FmAsYg)

![](sim_cpu.png)

- 8 bit CPU architecture
- 16 different instructions based on the suitability of our
- Our computer has a 4-bit opcode, 4-bit address length.
- A memory of 16x8.
- Eight registers: IR, PC, A, B, OR, MBR, MAR and SC.
- Binary to 7 Segment converter
- An 8-bit internal Bus.
- 4-bit and 8-bit External Bus.

# <span class="c29">Chapter 1: INTRODUCTION</span>

<span class="c5"></span>

<span class="c6">I have implemented 16 different instructions based on
the suitability of our project. Our computer has a 4-bit opcode, 4-bit
address length. With that being said, our computer “Quintuple-A”
consists of the following hardware components:</span>

1. A <span class="c56">memory</span><span class="c6"> of 16x8.</span>

2. Eight registers: <span class="c56">IR, PC, A, B, OR, MBR, MAR
   </span>and <span class="c56">SC</span><span class="c6">.</span>

<span class="c6">3. Binary to 7 Segment converter </span>

<span class="c6">4. An 8-bit internal Bus.</span>

<span class="c6">5. 4-bit and 8-bit External Bus.</span>

<span class="c6">6. Control Unit Design using Logisim combinational
analysis</span>

<span class="c6">7. ALU that supports adding, subtracting, XOR, AND, OR
etc</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

---

<span class="c6"></span>

# <span class="c29">Chapter 2: Design Considerations</span>

<span class="c5"></span>

## <span class="c38">2.1. INSTRUCTION FORMAT</span>

<span class="c6">There are two parts an instruction can be divided into.
They are:</span>

<span class="c56">Operation Code (Opcode)</span><span class="c6">: It
specifies the operation for an instruction.</span>

<span class="c56">Address</span><span class="c6">: It specifies the
registers and/or locations in memory to use for a particular</span>

<span class="c6">Operation</span>

<span class="c6"> An 8 bit computer by design should have a word size of
8 bits. Memory address register, which is responsible for storing RAM
addresses, is 4 bit.  so the size of RAM is 2^4 = 16 bytes only. </span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 481.00px; height: 91.00px;"><img src="images/image8.png"
style="width: 481.00px; height: 91.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 1: Instruction Format</span>

<span class="c6"></span>

<span class="c5"></span>

## <span class="c38">2.2. ADDRESSING MODES</span>

<span class="c5"></span>

<span class="c5">Immediate Addressing</span>

<span class="c6"></span>

<span class="c6">The address of the operand is loaded directly into the
A register in immediate addressing mode. One of the example of immediate
addressing is given in the figure below.</span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 346.00px; height: 241.00px;"><img src="images/image7.png"
style="width: 346.00px; height: 241.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 2: Immediate Addressing</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c5">Direct Addressing</span>

<span class="c5"></span>

<span class="c6">The address of the operand is stored in the memory
location specified in the instruction in the direct addressing
mode</span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 442.00px; height: 282.00px;"><img src="images/image10.png"
style="width: 442.00px; height: 282.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 3: Direct Addressing mode</span>

<span class="c5"></span>

## <span class="c38">2.3. INSTRUCTION SET</span>

<span class="c5"></span>

Since I allocated 4 bits for opcode, only 16 total instructions are
possible. However I wanted to make this computer as simple as possible
so I only added 2<span class="c67">4 </span><span class="c6">=16 total
instructions. Furthermore among those 16 instructions 8 of them has been
divided into register. Below is the table that shows Register reference
operations and memory reference instructions</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c5">Register Reference Instruction</span>

<span class="c5"></span>

<span class="c6">Register reference instruction work with registers
only</span>

<span class="c6"></span>

<span id="t.d60e237ecb87f5d98172c5bc08b94f5c6979d199"></span><span id="t.0"></span>

<table class="c44">
<tbody>
<tr class="odd c22">
<td class="c36"><p><span class="c5">Opcode </span></p></td>
<td class="c72"><p><span class="c5">Instruction</span></p></td>
<td class="c47"><p><span class="c5">Description</span></p></td>
</tr>
<tr class="even c22">
<td class="c36"><p><span class="c6">1011</span></p></td>
<td class="c72"><p><span class="c6">CLEAR</span></p></td>
<td class="c47"><p><span class="c6">Set OR to 0</span></p></td>
</tr>
<tr class="odd c22">
<td class="c36"><p><span class="c6">1100</span></p></td>
<td class="c72"><p><span class="c6">INC </span></p></td>
<td class="c47"><p><span class="c6">Increment Output
Register</span></p></td>
</tr>
<tr class="even c22">
<td class="c36"><p><span class="c6">1101</span></p></td>
<td class="c72"><p><span class="c6">COMPLEMENT</span></p></td>
<td class="c47"><p><span class="c6">Complement Output
Register</span></p></td>
</tr>
<tr class="odd c22">
<td class="c36"><p><span class="c6">1110</span></p></td>
<td class="c72"><p><span class="c6">SHL </span></p></td>
<td class="c47"><p><span class="c6"> Shift Left Output
Register</span></p></td>
</tr>
<tr class="even c22">
<td class="c36"><p><span class="c6">1111</span></p></td>
<td class="c72"><p><span class="c6">SHR</span></p></td>
<td class="c47"><p><span class="c6">Shift Right Output
Register</span></p></td>
</tr>
<tr class="odd c22">
<td class="c36"><p><span class="c6">1000</span></p></td>
<td class="c72"><p><span class="c6">SWAP</span></p></td>
<td class="c47"><p><span class="c6">SWAP Register A and B
Values</span></p></td>
</tr>
</tbody>
</table>

<span class="c55">Table 1: Register Reference Instruction</span>

---

<span class="c38"></span>

## <span class="c38">2.4. MEMORY REFERENCE INSTRUCTIONS</span>

<span class="c5"></span>

<span class="c6">Memory reference instructions load values into and
store values from the general registers. </span>

<span id="t.562582e2ebc61b8955744e01ed2bd445708c89dd"></span><span id="t.1"></span>

<table class="c44">
<tbody>
<tr class="odd c22">
<td class="c36"><p><span class="c5">Opcode </span></p></td>
<td class="c4"><p><span class="c5">Instruction</span></p></td>
<td class="c53"><p><span class="c5">Description</span></p></td>
</tr>
<tr class="even c22">
<td class="c36"><p><span class="c6">0000</span></p></td>
<td class="c4"><p><span class="c6">LOAD A, [M]</span></p></td>
<td class="c53"><p><span class="c6">Load the contents of M into A
Register</span></p></td>
</tr>
<tr class="odd c22">
<td class="c36"><p><span class="c6">0001</span></p></td>
<td class="c4"><p><span class="c6">LOAD B, [M]</span></p></td>
<td class="c53"><p><span class="c6">Load the contents of M into B
Register</span></p></td>
</tr>
<tr class="even c22">
<td class="c36"><p><span class="c6">1001</span></p></td>
<td class="c4"><p><span class="c6">LDI A, M</span></p></td>
<td class="c53"><p><span class="c6">Load content M into A
register</span></p></td>
</tr>
<tr class="odd c22">
<td class="c36"><p><span class="c6">1010</span></p></td>
<td class="c4"><p><span class="c6">LDI B, M</span></p></td>
<td class="c53"><p><span class="c6">Load content M into B
register</span></p></td>
</tr>
<tr class="even c54">
<td class="c36"><p><span class="c6">0010</span></p></td>
<td class="c4"><p><span class="c6">ADD </span></p></td>
<td class="c53"><p><span class="c6">Add A and B</span></p></td>
</tr>
<tr class="odd c22">
<td class="c36"><p><span class="c6">0011</span></p></td>
<td class="c4"><p><span class="c6">STORE [M]</span></p></td>
<td class="c53"><p><span class="c6">Store the contents of output
Register to given memory location</span></p></td>
</tr>
<tr class="even c22">
<td class="c36"><p><span class="c6">0100</span></p></td>
<td class="c4"><p><span class="c6">SUB</span></p></td>
<td class="c53"><p><span class="c6">Subtract A and B</span></p></td>
</tr>
<tr class="odd c22">
<td class="c36"><p><span class="c6">0101</span></p></td>
<td class="c4"><p><span class="c6">XOR</span></p></td>
<td class="c53"><p><span class="c6">XOR operation on A and
B</span></p></td>
</tr>
<tr class="even c22">
<td class="c36"><p><span class="c6">0110</span></p></td>
<td class="c4"><p><span class="c6">AND</span></p></td>
<td class="c53"><p><span class="c6">AND operation on A and
B</span></p></td>
</tr>
<tr class="odd c22">
<td class="c36"><p><span class="c6">0111</span></p></td>
<td class="c4"><p><span class="c6">OR</span></p></td>
<td class="c53"><p><span class="c6">OR operation on A and
B</span></p></td>
</tr>
</tbody>
</table>

<span class="c55">Table 2: Memory Reference Instruction</span>

<span class="c5"></span>

<span class="c6"></span>

<span class="c5"></span>

---

<span class="c38"></span>

# <span class="c29">Chapter 3: DESIGN OF INDIVIDUAL COMPONENT</span>

<span class="c6"></span>

## <span class="c38">3.1. REGISTER</span>

<span class="c6"></span>

<span class="c6">A single bit can be persisted using D Flip flop.
Furthermore these 8 cells make up a 8-bit register. Since D flip flop
doesn’t have input pins for control like WE, Din. I can add it using a
combination of AND, OR gates and controlled Buffer.</span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 391.00px; height: 129.00px;"><img src="images/image9.png"
style="width: 391.00px; height: 129.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 4: A D-Flip Flop</span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 468.83px; height: 307.10px;"><img src="images/image12.png"
style="width: 468.83px; height: 307.10px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 5: Memory Cell</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 380.00px;"><img src="images/image11.png"
style="width: 624.00px; height: 380.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 6: 8 bit Register built using Memory
cells</span>

<span class="c6"></span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 417.05px; height: 325.50px;"><img src="images/image14.png"
style="width: 417.05px; height: 325.50px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 7: 4 Bit Memory Address Register</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6">Our Computer consists of 8 Registers. They are as
follows</span>

<span class="c6"></span>

<span class="c5">Instruction Register (IR)</span>

<span class="c79">Size: 8 bits</span>

<span class="c6">IR stores the 8 bits of instruction read from the
memory. At the start of each instruction cycle, the address contained in
the PC is transferred to the MAR, and the content of the memory location
pointer by MAR is then transferred to the IR through the internal bus
system (IBS). Once the instruction is loaded in the IR, Opcode is
selected with Binary selector by Control Unit and if opcode requires
address to be loaded then the address line is selected and sent to
MAR.</span>

<span class="c6"></span>

<span class="c6"></span>

---

<span class="c5"></span>

<span class="c5">Program Counter (PC)</span>

<span class="c43">Size: 3 Bits</span>

<span class="c6">The program counter contains the address of the memory
location where the next instruction is located. At the beginning of each
instruction cycle (fetch), the content of the program counter is
transferred to MAR and then is incremented by one to point to the next
consecutive location.</span>

<span class="c6"></span>

<span class="c5">Memory Address Register (MAR)</span>

<span class="c43">Size: 4 bits</span>

<span class="c6">It contains main memory addresses of data and
instructions. It holds the memory location of data that needs to be
accessed</span>

<span class="c6"></span>

<span class="c5">Memory Buffer Register (MBR)</span>

<span class="c6">Size: 8 bits</span>

<span class="c6">MBR acts as a buffer between RAM and other Registers.
When loading something into the instruction register, the contents gets
loaded into MBR first then only into IR through the internal bus. When
something needs to be written into RAM then content to be loaded is
first placed on MBR then written to RAM</span>

<span class="c6"></span>

<span class="c5">Output Register (OR)</span>

<span class="c6">Size: 8 bits</span>

<span class="c6">It stores the output value of ALU. </span>

<span class="c6"></span>

<span class="c5">A Register </span>

<span class="c6">Size: 8 bits</span>

<span class="c6">This is one of the registers readily available to
programmers and where data can be loaded so that ALU can interface it
with.</span>

<span class="c6"></span>

---

<span class="c5"></span>

<span class="c5">B Register</span>

<span class="c6">Size: 8 bits</span>

<span class="c6">This is one of the registers readily available to
programmers and where data can be loaded so that ALU can interface it
with.</span>

<span class="c6"></span>

<span class="c5">Sequence Counter (SC)</span>

<span class="c6">Size: 3 bits</span>

<span class="c6">Sequence Counter is incremented with respect to clock
cycle and resets when instruction is finished or halted. </span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

---

<span class="c5"></span>

## <span class="c38">3.2. COUNTER</span>

<span class="c6"></span>

<span class="c56">Ripple counter </span>is a cascaded arrangement of
flip-flops where the output of one flip-flop drives the clock input of
the following flip-flop. The number of flip flops in the cascaded
arrangement depends upon the number of different logic states that it
goes through before it repeats the sequence. A n-bit ripple counter can
count up to 2<span class="c67">n</span><span class="c6"> states</span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 529.50px; height: 230.81px;"><img src="images/image13.png"
style="width: 529.50px; height: 230.81px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 8: Ripple Counter that works on Falling
edge</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6">Instead of using a clock pulse I can use the same input
to increment the counter if count-enable is set to high. The cascaded
arrangement allows one counter to activate another. </span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 456.50px; height: 338.72px;"><img src="images/image17.png"
style="width: 456.50px; height: 338.72px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 9: Waveform of ripple counter</span>

<span class="c6"></span>

<span class="c6"></span>

3.3. <span class="c56">MEMORY UNIT</span>

<span class="c43"></span>

<span class="c43">Size: 16x8</span>

The memory size 16x8 indicates there are 16 different slots where 8 bits
of instruction can be stored and executed in each slot. Memory stores
both the instruction and the data on which processing is to be
performed.  To address 16 different slots
log<span class="c84">2</span><span class="c6">(16) = 4-bit address line
is needed. </span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 423.18px; height: 350.28px;"><img src="images/image15.png"
style="width: 423.18px; height: 350.28px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 10: Block diagram for 4x4 sized RAM</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6">Half of the ram is to be used for instruction and half
of it is to be used for data. </span>

<span class="c6"></span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 391.00px; height: 321.00px;"><img src="images/image16.png"
style="width: 391.00px; height: 321.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 11: Memory unit division into Instruction and
Data</span>

<span class="c6"></span>

<span class="c43">Note: it is just a convention</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

---

<span class="c38"></span>

## <span class="c38">3.3. PROGRAMMING 7 SEGMENT DISPLAY</span>

<span class="c6"></span>

<span class="c6">For the output the best way to show the results is in
the Decimal system. I have a register size of 8 bits which means 2^8-1
is the largest number I have to compute for. Logisim has a ROM device
which can load hex values from the external file. To map binary number
to equivalent decimal representation following hex table was used</span>

<span class="c6"></span>

<span class="c6"></span>

<span id="t.fb717596f67e84273672cdd0b4f46d1e220ed98a"></span><span id="t.2"></span>

<table class="c44">
<tbody>
<tr class="odd c22">
<td class="c64"><p><span class="c6">Decimal</span></p></td>
<td class="c61"><p><span class="c6">Binary</span></p></td>
<td class="c65"><p><span class="c6">Seven Segment
Display</span></p></td>
</tr>
<tr class="even c22">
<td class="c64"><p><span class="c6">0</span></p></td>
<td class="c61"><p><span class="c6">0000</span></p></td>
<td class="c65"><p><span class="c6">11100111</span></p></td>
</tr>
<tr class="odd c22">
<td class="c64"><p><span class="c6">1</span></p></td>
<td class="c61"><p><span class="c6">0001</span></p></td>
<td class="c65"><p><span class="c6">0010001</span></p></td>
</tr>
<tr class="even c22">
<td class="c64"><p><span class="c6">2</span></p></td>
<td class="c61"><p><span class="c6">0010</span></p></td>
<td class="c65"><p><span class="c6">11001011</span></p></td>
</tr>
<tr class="odd c22">
<td class="c64"><p><span class="c6">3</span></p></td>
<td class="c61"><p><span class="c6">0011</span></p></td>
<td class="c65"><p><span class="c6">01101011</span></p></td>
</tr>
<tr class="even c22">
<td class="c64"><p><span class="c6">4</span></p></td>
<td class="c61"><p><span class="c6">0100</span></p></td>
<td class="c65"><p><span class="c6">00101101</span></p></td>
</tr>
<tr class="odd c22">
<td class="c64"><p><span class="c6">5</span></p></td>
<td class="c61"><p><span class="c6">0101</span></p></td>
<td class="c65"><p><span class="c6">01101110</span></p></td>
</tr>
<tr class="even c22">
<td class="c64"><p><span class="c6">6</span></p></td>
<td class="c61"><p><span class="c6">0110</span></p></td>
<td class="c65"><p><span class="c6">11101110</span></p></td>
</tr>
<tr class="odd c22">
<td class="c64"><p><span class="c6">7</span></p></td>
<td class="c61"><p><span class="c6">0111</span></p></td>
<td class="c65"><p><span class="c6">00010001</span></p></td>
</tr>
<tr class="even c22">
<td class="c64"><p><span class="c6">8</span></p></td>
<td class="c61"><p><span class="c6">1000</span></p></td>
<td class="c65"><p><span class="c6">11110111</span></p></td>
</tr>
<tr class="odd c22">
<td class="c64"><p><span class="c6">9</span></p></td>
<td class="c61"><p><span class="c6">1001</span></p></td>
<td class="c65"><p><span class="c6">11011111</span></p></td>
</tr>
</tbody>
</table>

<span class="c55">Table 3: Decimal Binary and its equivalent Seven
segment Display Code</span>

<span class="c6"></span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 404.50px; height: 253.80px;"><img src="images/image18.png"
style="width: 404.50px; height: 253.80px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 12: Binary to 7 segment converter.</span>

<span class="c6"></span>

<span class="c6">Circuit takes 00011101 as input and shows 29 as output.
Binary to Decimal Conversion using ROM. To convert binary to seven
segment displayable values. Each binary value that is addressable on ROM
has a corresponding 7 segment values placed on it which means if i
address 100 then the output will be 00101101 which shows 4 on a seven
segment display. To program the data to be loaded on ROM, a very simple
approach is used. </span>

<span class="c6">If number is 652 then first it is divided into its
corresponding digits and stored in unsigned 32 bit storage</span>

<span class="c6"></span>

<span class="c6">652 MOD 10 = 2 = 11001011 </span>

<span class="c6">65 MOD 10 = 5 = 01101110</span>

<span class="c6">6 MOD 10 = 6 = 11101110 </span>

<span class="c6"></span>

<span class="c6">11001011 &lt;&lt; 0 = 00000000 00000000 00000000
11001011</span>

<span class="c6">01101110 &lt;&lt; 8 = 00000000 00000000 01101110
 00000000</span>

<span class="c6">11101110 &lt;&lt; 16 = 00000000 11101110 00000000
00000000</span>

<span class="c6"></span>

<span class="c6">Then these numbers are added.</span>

<span class="c6">Code used to convert Binary to Seven Segment Display
Values in Rust is:</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">fs</span><span class="c12">::</span><span class="c9">File</span><span class="c3">;</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">io</span><span class="c12">::</span><span class="c9">Write</span><span class="c3">;</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">fs</span><span class="c12">::</span><span class="c9">OpenOptions</span><span class="c3">;</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">io</span><span class="c12">::</span><span class="c37">prelude</span><span class="c3">::\*;</span>

<span class="c12">fn</span><span class="c10"> </span><span class="c0">main</span><span class="c12">()</span><span class="c10"> </span><span class="c3">{</span>

<span class="c26 c10"></span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">file</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">OpenOptions</span><span class="c12">::</span><span class="c0">new</span><span class="c12">().</span><span class="c0">write</span><span class="c12">(</span><span class="c51">true</span><span class="c12">).</span><span class="c0">create</span><span class="c12">(</span><span class="c51">true</span><span class="c12">).</span><span class="c0">open</span><span class="c12">("</span><span class="c48">seven-segment-rom</span><span class="c12">").</span><span class="c0">expect</span><span class="c12">("</span><span class="c48">couldn't</span><span class="c3">");</span>

<span class="c10">   
</span><span class="c0">writeln!</span><span class="c12">(&</span><span class="c52">mut</span><span class="c10"> </span><span class="c9">file</span><span class="c12">,"</span><span class="c48">v2.0
raw</span><span class="c3">");</span>

<span class="c26 c10"></span>

<span class="c26 c10"></span>

<span class="c56 c57">    // 0 -&gt; 11100111</span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c9">segment\_values</span><span class="c10"> </span><span class="c12">:</span><span class="c10"> </span><span class="c12">\[</span><span class="c9">u8</span><span class="c12">;</span><span class="c10"> </span><span class="c51">10</span><span class="c12">\]</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c12">\[</span><span class="c51">0b11100111</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b00100001</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b11001011</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b01101011</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b00101101</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b01101110</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b11101110</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b00100011</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b11101111</span><span class="c12">,</span><span class="c10"> </span><span class="c51">0b01101111</span><span class="c3">\];</span>

<span class="c10">   
</span><span class="c2">for</span><span class="c10"> </span><span class="c9">i</span><span class="c10"> </span><span class="c12">in</span><span class="c10"> </span><span class="c51">0</span><span class="c12">..=</span><span class="c51">255</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">       
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">shift\_counter</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c51">0</span><span class="c3">;</span>

<span class="c10">       
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">buffer\_value</span><span class="c10"> </span><span class="c12">:</span><span class="c10"> </span><span class="c9">u32</span><span class="c12">=</span><span class="c10"> </span><span class="c51">0</span><span class="c3">;</span>

<span class="c10">       
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">temp\_i</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">i</span><span class="c3">;</span>

<span class="c10">       
</span><span class="c2">if</span><span class="c10"> </span><span class="c9">i</span><span class="c10"> </span><span class="c46">==</span><span class="c10"> </span><span class="c51">0</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">           
</span><span class="c0">write!</span><span class="c12">(&</span><span class="c52">mut</span><span class="c10"> </span><span class="c9">file</span><span class="c12">,"{</span><span class="c48">:x</span><span class="c12">}</span><span class="c48"> </span><span class="c12">",</span><span class="c10"> </span><span class="c9">segment\_values</span><span class="c12">\[</span><span class="c9">i</span><span class="c12">\]</span><span class="c10"> </span><span class="c12">as</span><span class="c10"> </span><span class="c9">u32</span><span class="c3">);</span>

<span class="c10">           
</span><span class="c2">continue</span><span class="c3">;</span>

<span class="c10">        </span><span class="c3">}</span>

<span class="c10">       
</span><span class="c2">while</span><span class="c10"> </span><span class="c9">temp\_i</span><span class="c10"> </span><span class="c46">&gt;</span><span class="c10"> </span><span class="c51">0</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">           
</span><span class="c2">let</span><span class="c10"> </span><span class="c9">digit</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">temp\_i</span><span class="c10"> </span><span class="c12">%</span><span class="c10"> </span><span class="c51">10</span><span class="c3">;</span>

<span class="c10">           
</span><span class="c9">buffer\_value</span><span class="c10"> </span><span class="c12">+=</span><span class="c10"> </span><span class="c12">(</span><span class="c9">segment\_values</span><span class="c12">\[</span><span class="c9">digit</span><span class="c12">\]</span><span class="c10"> </span><span class="c12">as</span><span class="c10"> </span><span class="c9">u32</span><span class="c12">)</span><span class="c10"> </span><span class="c46">&lt;&lt;</span><span class="c10"> </span><span class="c12">(</span><span class="c51">8</span><span class="c10"> </span><span class="c12">\*</span><span class="c10"> </span><span class="c9">shift\_counter</span><span class="c3">);</span>

<span class="c10">           
</span><span class="c9">shift\_counter</span><span class="c10"> </span><span class="c12">+=</span><span class="c10"> </span><span class="c51">1</span><span class="c3">;</span>

<span class="c10">           
</span><span class="c9">temp\_i</span><span class="c10"> </span><span class="c12">/=</span><span class="c10"> </span><span class="c51">10</span><span class="c3">;</span>

<span class="c10">        </span><span class="c3">}</span>

<span class="c10">       
</span><span class="c0">write!</span><span class="c12">(&</span><span class="c52">mut</span><span class="c10"> </span><span class="c9">file</span><span class="c12">,"{</span><span class="c48">:x</span><span class="c12">}</span><span class="c48"> </span><span class="c12">",</span><span class="c10"> </span><span class="c9">buffer\_value</span><span class="c3">);</span>

<span class="c10">       
</span><span class="c2">if</span><span class="c10"> </span><span class="c12">(</span><span class="c9">i</span><span class="c12">+</span><span class="c51">1</span><span class="c12">)</span><span class="c10"> </span><span class="c12">%</span><span class="c10"> </span><span class="c51">8</span><span class="c10"> </span><span class="c46">==</span><span class="c10"> </span><span class="c51">0</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">           
</span><span class="c0">writeln!</span><span class="c12">(&</span><span class="c52">mut</span><span class="c10"> </span><span class="c9">file</span><span class="c12">,</span><span class="c10"> </span><span class="c3">"");</span>

<span class="c10">        </span><span class="c3">}</span>

<span class="c10">    </span><span class="c3">}</span>

<span class="c3">}</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

---

<span class="c38"></span>

## <span class="c38">3.4. ARITHMETIC AND LOGICAL UNIT (ALU)</span>

<span class="c6">The arithmetic and logic unit in our computer performs
arithmetic and logical operations. The design procedure starts with
building a full adder which has 2 AND gates, 2 XOR gates and 1 OR
gate.</span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 439.94px; height: 277.10px;"><img src="images/image19.png"
style="width: 439.94px; height: 277.10px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 13: Full adder</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6">Full adder works only for one bit. Since our computer
is 8 bits I have to extend the full adder and add two 8-bit input pins
and one 8-bit output pins. </span>

<span class="c6"></span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 469.33px;"><img src="images/image20.png"
style="width: 624.00px; height: 469.33px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 14: 8 Bit Adder</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6">Instruction set supports not only adding but
subtracting, ANDing, XORing and ORing also. To support subtraction, I
can complement one of the registers and add one to the result. Addition
and subtraction can have the same line which can be enabled if the ADD
input line or SUB input line is high. For other operations each of them
can have their own line and can be activated in a similar way. </span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 413.33px;"><img src="images/image21.png"
style="width: 624.00px; height: 413.33px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 15: Adder, Subtractor, XORer, ANDer and
ORer.</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

## <span class="c38">3.5. CONTROL UNIT</span>

<span class="c6">Control unit is implemented by using the Logisim
combinational analysis tool. First input signals given by IR(Instruction
Register) for opcode OPC0, OPC1, OPC2 and OPC3 with the input signal
given by sequence counter are added. Then for timing and control
Sequence counter pins SC0, SC1, and SC2 are added. The output pins
C0..C27 with description is present on the table below</span>

<span class="c6"></span>

<span id="t.91a7f8e76f089d7cd7ef46d6923e3884557f64cf"></span><span id="t.3"></span>

<span class="c6">C0</span>

<span class="c6">PC OUTPUT ENABLE</span>

<span class="c6">C1</span>

<span class="c6">PC COUNT ENABLE</span>

<span class="c6">C2 </span>

<span class="c6">RAM WRITE ENABLE</span>

<span class="c6">C3</span>

<span class="c6">RAM OUTPUT ENABLE</span>

<span class="c6">C4</span>

<span class="c6">MBR WRITE ENABLE</span>

<span class="c6">C5</span>

<span class="c6">MBR INTERNAL BUS ENABLE</span>

<span class="c6">C6</span>

<span class="c6">MBR OUTPUT ENABLE</span>

<span class="c6">C7</span>

<span class="c6">IR WRITE ENABLE</span>

<span class="c6">C8</span>

<span class="c6">IR OUTPUT ENABLE</span>

<span class="c6">C9</span>

<span class="c6">MAR WRITE ENABLE</span>

<span class="c6">C10</span>

<span class="c6">MAR OUTPUT ENABLE</span>

<span class="c6">C11</span>

<span class="c6">ALU OUTPUT ENABLE</span>

<span class="c6">C12</span>

<span class="c6">REGISTER A WRITE ENABLE</span>

<span class="c6">C13</span>

<span class="c6">REGISTER B WRITE ENABLE</span>

<span class="c6">C14</span>

<span class="c6">OUTPUT REGISTER OUTPUT ENABLE</span>

<span class="c6">C15</span>

<span class="c6">OUTPUT REGISTER WRITE ENABLE</span>

<span class="c6">C16</span>

<span class="c6">ALU SUBTRACT MODE </span>

<span class="c6">C17</span>

<span class="c6">ALU XOR MODE</span>

<span class="c6">C18</span>

<span class="c6">ALU AND MODE</span>

<span class="c6">C19</span>

<span class="c6">ALU OR MODE</span>

<span class="c6">C20</span>

<span class="c6">REGISTER A OUTPUT ENABLE</span>

<span class="c6">C21</span>

<span class="c6">REGISTER B OUTPUT ENABLE</span>

<span class="c6">C22</span>

<span class="c6"> RESET FOR OUTPUT REGISTER (OR)</span>

<span class="c6">C23</span>

<span class="c6">COMPLEMENT FOR OUTPUT REGISTER(OR)</span>

<span class="c6">C24</span>

<span class="c6">SHIFT RIGHT ENABLE FOR OUTPUT REGISTER </span>

<span class="c6">C25</span>

<span class="c6">SHIFT LEFT ENABLE FOR OUTPUT REGISTER</span>

<span class="c6">C26</span>

<span class="c6">INC FOR OUTPUT REGISTER</span>

<span class="c6">C27</span>

<span class="c6">IMMEDIATE LOAD ENABLE(ILE) PIN ENABLE</span>

<span class="c55">Table 4: Control Unit</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

---

## <span class="c38">3.6. BUS SYSTEM AND OVERALL ARCHITECTURE</span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 612.50px; height: 472.00px;"><img src="images/image22.png"
style="width: 612.50px; height: 472.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 16: Computer Architecture</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

---

<span class="c38"></span>

## <span class="c38">3.7. INSTRUCTION SET DESIGN</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6">INITIAL OPERATION</span>

<span class="c6">A computer can understand and execute a few numbers of
instructions that are hardwired in its design, these instructions form
the instruction set of the computer.</span>

<span class="c6">The selection of binary code for the instruction and
the instruction itself is the main task of the computer designer.</span>

<span class="c6"></span>

<span class="c6">A machine instruction is executed in the following
cycle</span>

<span class="c6"></span>

<span class="c56">Fetch Cycle</span><span class="c6">: Here, the
instruction is fetched from the memory.</span>

<span class="c56">Decode Cycle</span><span class="c6">: After fetching
the instructions, they are decoded in this cycle.</span>

<span class="c6">This mainly happens in the T2 cycle. Here, the decision
is taken such that the</span>

<span class="c6">instructions are sent accordingly to the respective
addressing modes.</span>

<span class="c56">Execution Cycle</span><span class="c6">: Once, the
decision of sending to the addressing modes are</span>

<span class="c6">taken, the instructions are finally executed in this
phase.</span>

<span class="c6"></span>

<span id="t.1d36d67e84dfdfad8ec96e9c7d8032c23c3b3162"></span><span id="t.4"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c7">
<td colspan="3" class="c75"><p><span class="c6">Fetch Decode and Execute
Cycle</span></p></td>
</tr>
<tr class="even c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="odd c23">
<td rowspan="2" class="c41"><p><span class="c6">T0 = 000</span></p>
<p><span class="c6"></span></p></td>
<td class="c11"><p><span class="c6">Activate OE of PC</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C0.C9 : MAR &lt;-
PC</span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="even c7">
<td class="c11"><p><span class="c6">Activate I of MAR</span></p></td>
</tr>
<tr class="odd c7">
<td rowspan="4" class="c41"><p><span class="c6">T1 = 001</span></p>
<p><span class="c6"></span></p></td>
<td class="c11"><p><span class="c6">Activate OE of MAR</span></p></td>
<td rowspan="4" class="c18"><p><span class="c6">C1.C3.C4.C10 : MBR &lt;-
[MAR], PC &lt;- PC + 1</span></p></td>
</tr>
<tr class="even c7">
<td class="c11"><p><span class="c6">Activate OE of RAM</span></p></td>
</tr>
<tr class="odd c7">
<td class="c11"><p><span class="c6">  Activate I of MBR</span></p></td>
</tr>
<tr class="even c7">
<td class="c11"><p><span class="c6">Activate CE of PC</span></p></td>
</tr>
<tr class="odd c7">
<td rowspan="2" class="c41"><p><span class="c6">T2 = 010</span></p></td>
<td class="c11"><p><span class="c6">Activate Internal OE of
MBR</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C5.C7 : IR &lt;-
MBR</span></p></td>
</tr>
<tr class="even c7">
<td class="c11"><p><span class="c6">Activate I of IR</span></p></td>
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c5">ADD OPERATION</span>

<span class="c6"></span>

<span id="t.8196fba863fa7687c18820a98781be5d2180b3ae"></span><span id="t.5"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T3 = 011</span></p></td>
<td rowspan="2" class="c11"><p><span class="c6">Activate OE of
ALU</span></p>
<p><span class="c6">Activate I of Output Register</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C15.C11: ALU &lt;- A +
B,</span></p>
<p><span class="c6">OR &lt;- ALU</span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c7">
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c6"></span>

<span class="c56">SUBTRACT OPERATION</span>

<span class="c6"></span>

<span id="t.52a5136fc1269ef7f461a39475c49d4eaf7b49b6"></span><span id="t.6"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T3 = 011</span></p></td>
<td rowspan="2" class="c11"><p><span class="c6">Activate OE of
ALU</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C15.C11.C16: ALU &lt;- A
- B,</span></p>
<p><span class="c6">OR &lt;- ALU</span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c7">
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5"></span>

---

<span class="c5">XOR OPERATION</span>

<span class="c6"></span>

<span id="t.7853d0e9702a53c0fb2598c1a1573c1c28cab3e7"></span><span id="t.7"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T3</span></p></td>
<td rowspan="2" class="c11"><p><span class="c6">Activate OE of
ALU</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C15.C11.C17: ALU &lt;- A
XOR B,</span></p>
<p><span class="c6">OR &lt;- ALU</span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c7">
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c5">AND OPERATION</span>

<span class="c6"></span>

<span id="t.4009c3a319ff4d38ce93a77eef667d267fa247ab"></span><span id="t.8"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T3</span></p></td>
<td rowspan="2" class="c11"><p><span class="c6">Activate OE of
ALU</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C15.C11.C18: ALU &lt;- A
AND B,</span></p>
<p><span class="c6">OR &lt;- ALU</span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c7">
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c6"></span>

<span class="c5">SWAP REGISTER VALUES</span>

<span class="c6"></span>

<span id="t.45929a9b49ff8fc57efe29dd421b1fc528067f44"></span><span id="t.9"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c60">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T3</span></p></td>
<td class="c11"><p><span class="c6">Activate OE of Register
A</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6"></span></p>
<p><span class="c6">C20.C15: OR &lt;- A</span></p></td>
</tr>
<tr class="odd c22">
<td class="c11"><p><span class="c6">Activate WR of OR</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T4</span></p></td>
<td class="c11"><p><span class="c6">Activate WR of Register
A</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C12.C21 : A &lt;-
B</span></p></td>
</tr>
<tr class="odd c7">
<td class="c11"><p><span class="c6">Activate OE of Register
B</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T5</span></p></td>
<td class="c11"><p><span class="c6">Activate WR of Register
B</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6"> C13.C14 : B &lt;-
OR</span></p></td>
</tr>
<tr class="odd c7">
<td class="c11"><p><span class="c6">Activate OE of OR </span></p></td>
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c5">LOAD A</span>

<span id="t.93c77dda07d0496dd5fef943cb57f6d44c64468b"></span><span id="t.10"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T3</span></p></td>
<td class="c11"><p><span class="c6">Activate OE of IR</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C8.C9 : MAR &lt;-
IR(4-7)</span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c7">
<td class="c11"><p><span class="c6">Activate I of MAR</span></p></td>
</tr>
<tr class="even c71">
<td rowspan="3" class="c41"><p><span class="c6">T4</span></p></td>
<td class="c11"><p><span class="c6">Activate OE of MAR</span></p></td>
<td rowspan="3" class="c18"><p><span class="c6">C3.C4.C10: MBR &lt;-
[MAR]</span></p></td>
</tr>
<tr class="odd c7">
<td class="c11"><p><span class="c6">Activate OE of RAM</span></p></td>
</tr>
<tr class="even c7">
<td class="c11"><p><span class="c6">Activate I of MBR</span></p></td>
</tr>
<tr class="odd c7">
<td rowspan="2" class="c41"><p><span class="c6">T5</span></p></td>
<td class="c11"><p><span class="c6">Activate internal OE of
MBR</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C5.C12: A &lt;-
MBR</span></p></td>
</tr>
<tr class="even c7">
<td class="c11"><p><span class="c6">Activate I of Reg. A</span></p></td>
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c5"></span>

<span class="c6"></span>

<span class="c5">LOAD TO B</span>

<span id="t.68b666c66a8c453e06b6a71498023bfdebcbd9fc"></span><span id="t.11"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T3</span></p></td>
<td class="c11"><p><span class="c6">Activate OE of IR</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C8.C9 : MAR &lt;-
IR(4-7)</span></p>
<p><span class="c6"></span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c7">
<td class="c11"><p><span class="c6">Activate I of MAR</span></p></td>
</tr>
<tr class="even c71">
<td rowspan="3" class="c41"><p><span class="c6">T4</span></p></td>
<td class="c11"><p><span class="c6">Activate OE of MAR</span></p></td>
<td rowspan="3" class="c18"><p><span class="c6">C3.C4.C10: MBR &lt;-
[MAR]</span></p></td>
</tr>
<tr class="odd c7">
<td class="c11"><p><span class="c6">Activate OE of RAM</span></p></td>
</tr>
<tr class="even c7">
<td class="c11"><p><span class="c6">Activate I of MBR</span></p></td>
</tr>
<tr class="odd c7">
<td rowspan="2" class="c41"><p><span class="c6">T5</span></p></td>
<td class="c11"><p><span class="c6">Activate internal OE of
MBR</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C5.C13: B &lt;-
MBR</span></p></td>
</tr>
<tr class="even c7">
<td class="c11"><p><span class="c6">Activate I of Reg. A</span></p></td>
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c5">STORE </span>

<span id="t.ffa4e21fa974e4c500292a9d26998c9c10b6ea21"></span><span id="t.12"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td rowspan="2" class="c41"><p><span class="c6">T3</span></p></td>
<td class="c11"><p><span class="c6">Activate OE of IR</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C8.C9: MAR &lt;-
IR(4-7)</span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c7">
<td class="c11"><p><span class="c6">Activate I of MAR</span></p></td>
</tr>
<tr class="even c63">
<td rowspan="2" class="c41"><p><span class="c6">T4</span></p></td>
<td class="c11"><p><span class="c6">Activate I of MBR</span></p></td>
<td rowspan="2" class="c18"><p><span class="c6">C4.C14: MBR &lt;- OR,
RAM &lt;- OR</span></p></td>
</tr>
<tr class="odd c63">
<td class="c11"><p><span class="c6">Activate OE of Output
Register</span></p></td>
</tr>
<tr class="even c63">
<td rowspan="3" class="c41"><p><span class="c6">T5</span></p></td>
<td class="c11"><p><span class="c6">Activate OE of MAR</span></p></td>
<td rowspan="3" class="c18"><p><span class="c6">C10.C2.C6: [MAR] &lt;-
MBR</span></p></td>
</tr>
<tr class="odd c63">
<td class="c11"><p><span class="c6">Activate I of RAM</span></p></td>
</tr>
<tr class="even c63">
<td class="c11"><p><span class="c6">Activate OE of MBR</span></p></td>
</tr>
</tbody>
</table>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

---

<span class="c5"></span>

<span class="c5">CLR</span>

<span class="c5"></span>

<span id="t.07745ac3ebb686010c4c3259891aec63ec8f1bfe"></span><span id="t.13"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c41"><p><span class="c6">Step Counter</span></p></td>
<td class="c11"><p><span class="c6">Operation to perform</span></p></td>
<td class="c18"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c7">
<td class="c41"><p><span class="c6">T3 = 011</span></p>
<p><span class="c6"></span></p>
<p><span class="c6">Sc0 =1 </span></p>
<p><span class="c6">Sc1 =1</span></p>
<p><span class="c6">sc2=0</span></p>
<p><span class="c6">Opc0 =1</span></p>
<p><span class="c6">Opc1 = 1</span></p>
<p><span class="c6">Opc2 = 0</span></p>
<p><span class="c6">Opc3 = 1</span></p>
<p><span class="c6"></span></p></td>
<td class="c11"><p><span class="c6">Activate Reset of </span></p>
<p><span class="c6">Output Register</span></p>
<p><span class="c6"> </span></p></td>
<td class="c18"><p><span class="c6">C22 : OR &lt;- 0</span></p>
<p><span class="c6"></span></p></td>
</tr>
</tbody>
</table>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5">INC</span>

<span class="c5"></span>

<span id="t.c2c38defc1e3d1cfabae828abab83f14e1315fba"></span><span id="t.14"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c70"><p><span class="c6">Step Counter</span></p></td>
<td class="c58"><p><span class="c6">Operation</span></p></td>
<td class="c58"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c78">
<td rowspan="2" class="c70"><p><span class="c6">T3</span></p></td>
<td rowspan="2" class="c58"><p><span class="c6">Activate INC of
OR</span></p></td>
<td rowspan="2" class="c58"><p><span class="c6">C26 : OR &lt;- OR +
1</span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c62">
</tr>
</tbody>
</table>

<span class="c5"></span>

<span class="c5"></span>

<span class="c5">SHL </span>

<span class="c5"></span>

<span id="t.2676b91e32db27d4480a3bda2036dfb44bcd9b6d"></span><span id="t.15"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c70"><p><span class="c6">Step Counter</span></p></td>
<td class="c58"><p><span class="c6">Operation</span></p></td>
<td class="c58"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c62">
<td rowspan="2" class="c70"><p><span class="c6">T3</span></p></td>
<td rowspan="2" class="c58"><p><span class="c6">Activate SHL of
OR</span></p></td>
<td rowspan="2" class="c58"><p><span class="c6">C25 : OR(0) &lt;- OR(1),
OR(1) &lt;- OR(2), OR(2) &lt;- OR(3), OR(3) &lt;- OR(4), OR(4) &lt;-
OR(5), OR(5) &lt;- OR(6), OR(6) &lt;- OR(7), OR(7) &lt;- OR(8), OR(8)
&lt;- 0 </span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c62">
</tr>
</tbody>
</table>

<span class="c5"></span>

<span class="c5">SHR</span>

<span class="c5"></span>

<span id="t.6e1a994ca5acb0ec435a3da50dbc00580cc941db"></span><span id="t.16"></span>

<table class="c44">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd c22">
<td class="c70"><p><span class="c6">Step Counter</span></p></td>
<td class="c58"><p><span class="c6">Operation</span></p></td>
<td class="c58"><p><span class="c6">RTL</span></p></td>
</tr>
<tr class="even c62">
<td rowspan="2" class="c70"><p><span class="c6">T3</span></p></td>
<td rowspan="2" class="c58"><p><span class="c6">Activate SHR of
OR</span></p></td>
<td rowspan="2" class="c58"><p><span class="c6">C24 : OR(8) &lt;- OR(7),
OR(7) &lt;- OR(6), OR(6) &lt;- OR(5), OR(5) &lt;- OR(4), OR(4) &lt;-
OR(3), OR(3) &lt;- OR(2), OR(2) &lt;- OR(1), OR(1) &lt;- OR(0), OR(0)
&lt;- 0 </span></p>
<p><span class="c6"></span></p></td>
</tr>
<tr class="odd c62">
</tr>
</tbody>
</table>

<span class="c5"></span>

<span class="c5"></span>

## <span class="c38"></span>

<span class="c5"></span>

## <span class="c38">3.8. TIMING AND CONTROL</span>

<span class="c6">The timing for all registers in the computer is
controlled by a master clock generator. The clock pulses are applied to
all flip flops and registers in the system, including the flip flops and
registers in the control unit. The clock pulses do not change the state
of the register unless the register is enabled by a control signal. The
control signals are generated in the control unit and provide control
inputs for the multiplexers in the common bus, control inputs in the
processor register and micro-operations hardwired organization for the
accumulator</span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 518.50px; height: 456.18px;"><img src="images/image23.png"
style="width: 518.50px; height: 456.18px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 514.50px; height: 369.00px;"><img src="images/image24.png"
style="width: 514.50px; height: 369.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Table 5: Control Unit for the Output pin C1-C11</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 505.50px; height: 424.00px;"><img src="images/image25.png"
style="width: 569.44px; height: 463.94px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 502.50px; height: 326.00px;"><img src="images/image1.png"
style="width: 508.51px; height: 326.00px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Table 6: Control Unit Table for Output pins C12 –
C21</span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 158.07px; height: 757.52px;"><img src="images/image2.png"
style="width: 158.07px; height: 757.52px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 256.44px; height: 569.31px;"><img src="images/image3.png"
style="width: 256.44px; height: 569.31px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 17:  Control Unit generated by Combinational
analysis after entering above table value on Logisim</span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 481.50px; height: 435.22px;"><img src="images/image4.png"
style="width: 481.50px; height: 435.22px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 18: Design of Sequence Counter and Control
Unit</span>

<span class="c6"></span>

<span class="c6"></span>

<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 322.67px;"><img src="images/image5.png"
style="width: 624.00px; height: 322.67px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" /></span>

<span class="c55">Figure 19: Whole CPU view in Logisim</span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c6"></span>

---

<span class="c38"></span>

## <span class="c38">3.9. ASSEMBLER </span>

<span class="c6"></span>

<span class="c6">An assembler is a program that takes basic computer
instructions and converts them into a pattern of bits that the
computer's processor can use to perform its basic operations</span>

<span class="c6">Its working principle is relatively simple. When
running assembler it expects filename as an argument. The file provided
is opened and read till the end. The escape character newline “\n” is
used to split and store an array of lines. Those lines are again split
with respect to &lt;SPACE&gt; and mapped into its uppercase form.
</span>

<span class="c6">Arrays of strings are now ready for pattern matching.
</span>

<span class="c6">Each index has a vector(fancy name for array that is
dynamically sized). </span>

<span class="c6">Our instruction has 3 main formats</span>

<span class="c6"></span>

- <span class="c6">\[OPCODE, REGISTER , ADDRESS\]</span>
- <span class="c6">\[OPCODE, ADDRESS\]</span>
- <span class="c6">\[OPCODE\]</span>

<span class="c6">These instructions are separated through rust pattern
matching features and then converted into equivalent hex For example the
code</span>

<span class="c6"></span>

<span class="c6">LOAD A 1100 =&gt; 0000 1100 =&gt; 1c</span>

<span class="c6">LOAD B 1101 =&gt; 0001 1101 =&gt; 1d</span>

<span class="c6">ADD  =&gt; 0010 0000 =&gt; 20</span>

<span class="c6">STORE 1100 =&gt; 0011 1100 =&gt;3c </span>

<span class="c6"></span>

<span class="c6">Assembler written in Rust:</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">fs</span><span class="c12">::</span><span class="c9">File</span><span class="c3">;</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">io</span><span class="c12">::</span><span class="c9">Write</span><span class="c3">;</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">fs</span><span class="c12">::</span><span class="c9">OpenOptions</span><span class="c3">;</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">io</span><span class="c12">::</span><span class="c37">prelude</span><span class="c3">::\*;</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">io</span><span class="c12">::{</span><span class="c9">Read</span><span class="c12">,</span><span class="c10"> </span><span class="c9">Seek</span><span class="c3">};</span>

<span class="c12">use</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">path</span><span class="c12">::</span><span class="c9">Path</span><span class="c3">;</span>

<span class="c26 c10"> </span>

<span class="c10 c26"> </span>

<span class="c12">fn</span><span class="c10"> </span><span class="c0">main</span><span class="c12">()</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c9">arg</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c37">std</span><span class="c12">::</span><span class="c37">env</span><span class="c12">::</span><span class="c0">args</span><span class="c12">().</span><span class="c0">nth</span><span class="c12">(</span><span class="c51">1</span><span class="c12">).</span><span class="c0">expect</span><span class="c12">("</span><span class="c48">Enter
file</span><span class="c3">");</span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c9">path</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">Path</span><span class="c12">::</span><span class="c0">new</span><span class="c12">(&</span><span class="c9">arg</span><span class="c3">);</span>

<span class="c26 c10"> </span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">file</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">OpenOptions</span><span class="c12">::</span><span class="c0">new</span><span class="c12">().</span><span class="c0">read</span><span class="c12">(</span><span class="c51">true</span><span class="c12">).</span><span class="c0">open</span><span class="c12">(</span><span class="c9">path</span><span class="c12">).</span><span class="c0">expect</span><span class="c12">("</span><span class="c48">couldn't
open file</span><span class="c3">");</span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">buf</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">String</span><span class="c12">::</span><span class="c0">new</span><span class="c3">();</span>

<span class="c10">   
</span><span class="c9">file</span><span class="c12">.</span><span class="c0">read\_to\_string</span><span class="c12">(&</span><span class="c52">mut</span><span class="c10"> </span><span class="c9">buf</span><span class="c12">).</span><span class="c0">unwrap</span><span class="c3">();</span>

<span class="c26 c10"> </span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">tokenized\_by\_line</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">buf</span><span class="c12">.</span><span class="c0">split</span><span class="c12">("</span><span class="c9">\\</span><span class="c12">n").</span><span class="c0">collect</span><span class="c12">::&lt;</span><span class="c9">Vec</span><span class="c12">&lt;&</span><span class="c9">str</span><span class="c3">&gt;&gt;();</span>

<span class="c26 c10"> </span>

<span class="c10">   
</span><span class="c0">println!</span><span class="c12">("{</span><span class="c48">:?</span><span class="c12">}",</span><span class="c10"> </span><span class="c9">tokenized\_by\_line</span><span class="c3">);</span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c9">tokenized\_form</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">tokenized\_by\_line</span><span class="c12">.</span><span class="c0">iter</span><span class="c12">().</span><span class="c0">map</span><span class="c12">(</span><span class="c46">|</span><span class="c12">&</span><span class="c9">val</span><span class="c46">|</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">       
</span><span class="c9">val</span><span class="c12">.</span><span class="c0">split</span><span class="c12">("</span><span class="c48"> </span><span class="c12">").</span><span class="c0">map</span><span class="c12">(</span><span class="c46">|</span><span class="c9">x</span><span class="c46">|</span><span class="c10"> </span><span class="c9">String</span><span class="c12">::</span><span class="c0">from</span><span class="c12">(</span><span class="c9">x</span><span class="c12">.</span><span class="c0">to\_uppercase</span><span class="c12">())).</span><span class="c0">filter</span><span class="c12">(</span><span class="c46">|</span><span class="c9">x</span><span class="c46">|</span><span class="c10"> </span><span class="c9">x</span><span class="c10"> </span><span class="c46">!=</span><span class="c10"> </span><span class="c12">"").</span><span class="c0">collect</span><span class="c12">::&lt;</span><span class="c9">Vec</span><span class="c12">&lt;</span><span class="c9">String</span><span class="c3">&gt;&gt;()</span>

<span class="c10">   
</span><span class="c12">}).</span><span class="c0">collect</span><span class="c12">::&lt;</span><span class="c9">Vec</span><span class="c12">&lt;</span><span class="c9">Vec</span><span class="c12">&lt;</span><span class="c9">String</span><span class="c3">&gt;&gt;&gt;();</span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">hex\_codes</span><span class="c12">:</span><span class="c10"> </span><span class="c9">Vec</span><span class="c12">&lt;</span><span class="c9">u8</span><span class="c12">&gt;</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">Vec</span><span class="c12">::</span><span class="c0">new</span><span class="c3">();</span>

<span class="c26 c10"> </span>

<span class="c26 c10"> </span>

<span class="c10">   
</span><span class="c2">for</span><span class="c10"> </span><span class="c12">(</span><span class="c9">i</span><span class="c12">,</span><span class="c9">tokens</span><span class="c12">)</span><span class="c10"> </span><span class="c12">in</span><span class="c10"> </span><span class="c9">tokenized\_form</span><span class="c12">.</span><span class="c0">iter</span><span class="c12">().</span><span class="c0">enumerate</span><span class="c12">()</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">       
</span><span class="c2">match</span><span class="c10"> </span><span class="c12">&</span><span class="c9">tokens</span><span class="c12">\[..\]</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">           
</span><span class="c12">\[</span><span class="c20">OP</span><span class="c12">,</span><span class="c10"> </span><span class="c20">REG</span><span class="c12">,</span><span class="c10"> </span><span class="c20">ADDR</span><span class="c12">\]</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">               
</span><span class="c2">match</span><span class="c10"> </span><span class="c12">&</span><span class="c20">OP</span><span class="c12">\[..\]</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">               
</span><span class="c12">"</span><span class="c48">LOAD</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                   
</span><span class="c2">let</span><span class="c10"> </span><span class="c9">digit</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">u8</span><span class="c12">::</span><span class="c0">from\_str\_radix</span><span class="c12">(&</span><span class="c20">ADDR</span><span class="c12">\[..\],</span><span class="c51">2</span><span class="c12">).</span><span class="c0">expect</span><span class="c12">("</span><span class="c48">LOAD
needs a address and the address you provided is not
valid</span><span class="c3">");</span>

<span class="c10">                   
</span><span class="c2">match</span><span class="c10"> </span><span class="c12">&</span><span class="c20">REG</span><span class="c12">\[..\]</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c12">"</span><span class="c48">A</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                           
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b000</span><span class="c3">);</span>

<span class="c10">                           
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c9">digit</span><span class="c3">);</span>

<span class="c10">                       
</span><span class="c3">},</span>

<span class="c10">                       
</span><span class="c12">"</span><span class="c48">B</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                           
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b0001</span><span class="c3">);</span>

<span class="c10">                           
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c9">digit</span><span class="c3">);</span>

<span class="c10">                       
</span><span class="c3">}</span>

<span class="c10">                       
</span><span class="c9">\_</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                           
</span><span class="c0">panic!</span><span class="c12">("</span><span class="c48">unknown
register. Available Register are A and B on Line
</span><span class="c12">{}",</span><span class="c10"> </span><span class="c9">i</span><span class="c3">);</span>

<span class="c10">                       
</span><span class="c3">}</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                </span><span class="c3">}</span>

<span class="c10">               
</span><span class="c12">"</span><span class="c48">LDI</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                   
</span><span class="c2">let</span><span class="c10"> </span><span class="c9">digit</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">u8</span><span class="c12">::</span><span class="c0">from\_str\_radix</span><span class="c12">(&</span><span class="c20">ADDR</span><span class="c12">\[..\],</span><span class="c51">2</span><span class="c12">).</span><span class="c0">expect</span><span class="c12">("</span><span class="c48">LDI
needs a address and the address you provided is not
valid</span><span class="c3">");</span>

<span class="c10">                   
</span><span class="c2">match</span><span class="c10"> </span><span class="c12">&</span><span class="c20">REG</span><span class="c12">\[..\]</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c12">"</span><span class="c48">A</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                           
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b1001</span><span class="c3">);</span>

<span class="c10">                           
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c9">digit</span><span class="c3">);</span>

<span class="c10">                       
</span><span class="c3">},</span>

<span class="c10">                       
</span><span class="c12">"</span><span class="c48">B</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                           
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b1010</span><span class="c3">);</span>

<span class="c10">                           
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c9">digit</span><span class="c3">);</span>

<span class="c10">                       
</span><span class="c3">}</span>

<span class="c10">                       
</span><span class="c9">\_</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                           
</span><span class="c0">panic!</span><span class="c12">("</span><span class="c48">unknown
register. Available Register are A and B on Line
</span><span class="c12">{}",</span><span class="c10"> </span><span class="c9">i</span><span class="c3">);</span>

<span class="c10">                       
</span><span class="c3">}</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                </span><span class="c3">}</span>

<span class="c10">               
</span><span class="c9">\_</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c12">{</span><span class="c10"> </span><span class="c0">panic!</span><span class="c12">("</span><span class="c48">unknown
OPCODE on line
</span><span class="c12">{}",</span><span class="c10"> </span><span class="c9">i</span><span class="c3">);}</span>

<span class="c10">            </span><span class="c3">}</span>

<span class="c10">            </span><span class="c3">}</span>

<span class="c10">           
</span><span class="c12">\[</span><span class="c20">OP</span><span class="c12">,</span><span class="c20">REG</span><span class="c12">\]</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">             
 </span><span class="c2">match</span><span class="c10"> </span><span class="c12">&</span><span class="c20">OP</span><span class="c12">\[..\]</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">               
</span><span class="c12">"</span><span class="c48">STORE</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                   
</span><span class="c2">let</span><span class="c10"> </span><span class="c9">digit</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">u8</span><span class="c12">::</span><span class="c0">from\_str\_radix</span><span class="c12">(&</span><span class="c20">REG</span><span class="c12">\[..\],</span><span class="c51">2</span><span class="c12">).</span><span class="c0">expect</span><span class="c12">("</span><span class="c48">STORE
needs a address and the address you provided is not
valid</span><span class="c3">");</span>

<span class="c10">                   
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b0011</span><span class="c3">);</span>

<span class="c10">                   
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c9">digit</span><span class="c3">);</span>

<span class="c10">                </span><span class="c3">}</span>

<span class="c10">               
</span><span class="c9">\_</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                   
</span><span class="c0">panic!</span><span class="c12">("</span><span class="c48">unknown
OPCODE on line
</span><span class="c12">{}",</span><span class="c10"> </span><span class="c9">i</span><span class="c3">);</span>

<span class="c10">                </span><span class="c3">}</span>

<span class="c10">               </span><span class="c3">}</span>

<span class="c10">            </span><span class="c3">}</span>

<span class="c10">           
</span><span class="c12">\[</span><span class="c20">OP</span><span class="c12">\]</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">               
</span><span class="c2">match</span><span class="c10"> </span><span class="c12">&</span><span class="c20">OP</span><span class="c12">\[..\]</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">ADD</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b0010</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">SUB</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b0100</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">XOR</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b0101</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">AND</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b0110</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">OR</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b0111</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">SWAP</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b1000</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">CLEAR</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b1000</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">INC</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b1000</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">COMPLEMENT</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b1000</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">SHL</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b1000</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c12">"</span><span class="c48">SHR</span><span class="c12">"</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b1000</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                   
</span><span class="c9">\_</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">                       
</span><span class="c0">panic!</span><span class="c12">("</span><span class="c48">unknown
OPCODE on line
</span><span class="c12">{}",</span><span class="c9">i</span><span class="c3">);</span>

<span class="c10">                    </span><span class="c3">}</span>

<span class="c10">                </span><span class="c3">}</span>

<span class="c10">               
</span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">push</span><span class="c12">(</span><span class="c51">0b0000</span><span class="c3">);</span>

<span class="c10">            </span><span class="c3">}</span>

<span class="c10">           
</span><span class="c12">\[\]</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c12">{</span><span class="c10"> </span><span class="c3">}</span>

<span class="c10">           
</span><span class="c12">\[..\]</span><span class="c10"> </span><span class="c12">=&gt;</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">               
</span><span class="c0">panic!</span><span class="c12">("</span><span class="c48">unexpected
Instruction on line
</span><span class="c12">{}",</span><span class="c10"> </span><span class="c9">i</span><span class="c3">);</span>

<span class="c10">            </span><span class="c3">}</span>

<span class="c10">        </span><span class="c3">}</span>

<span class="c10">    </span><span class="c3">}</span>

<span class="c10">   
</span><span class="c0">println!</span><span class="c12">("{</span><span class="c48">:?</span><span class="c12">}",</span><span class="c9">tokenized\_form</span><span class="c3">);</span>

<span class="c10">   
</span><span class="c0">println!</span><span class="c12">("{</span><span class="c48">:?</span><span class="c12">}",</span><span class="c9">hex\_codes</span><span class="c3">);</span>

<span class="c26 c10"> </span>

<span class="c10">   
</span><span class="c2">let</span><span class="c10"> </span><span class="c52">mut</span><span class="c10"> </span><span class="c9">new\_file</span><span class="c10"> </span><span class="c12">=</span><span class="c10"> </span><span class="c9">OpenOptions</span><span class="c12">::</span><span class="c0">new</span><span class="c12">().</span><span class="c0">create</span><span class="c12">(</span><span class="c51">true</span><span class="c12">).</span><span class="c0">write</span><span class="c12">(</span><span class="c51">true</span><span class="c12">).</span><span class="c0">open</span><span class="c12">(</span><span class="c9">path</span><span class="c12">.</span><span class="c0">with\_file\_name</span><span class="c12">(</span><span class="c9">path</span><span class="c12">.</span><span class="c0">file\_stem</span><span class="c12">().</span><span class="c0">unwrap</span><span class="c12">())).</span><span class="c0">expect</span><span class="c12">("</span><span class="c48">no
file</span><span class="c3">");</span>

<span class="c10">   
</span><span class="c0">writeln!</span><span class="c12">(&</span><span class="c52">mut</span><span class="c10"> </span><span class="c9">new\_file</span><span class="c12">,</span><span class="c10"> </span><span class="c12">"</span><span class="c48">v2.0
raw</span><span class="c3">");</span>

<span class="c10">   
</span><span class="c2">for</span><span class="c10"> </span><span class="c12">(</span><span class="c9">i</span><span class="c12">,</span><span class="c9">hex</span><span class="c12">)</span><span class="c10"> </span><span class="c12">in</span><span class="c10"> </span><span class="c9">hex\_codes</span><span class="c12">.</span><span class="c0">iter</span><span class="c12">().</span><span class="c0">enumerate</span><span class="c12">()</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">       
</span><span class="c0">write!</span><span class="c12">(&</span><span class="c52">mut</span><span class="c10"> </span><span class="c9">new\_file</span><span class="c12">,"{</span><span class="c48">:x</span><span class="c12">}",</span><span class="c10"> </span><span class="c9">hex</span><span class="c3">);</span>

<span class="c10">       
</span><span class="c2">if</span><span class="c10"> </span><span class="c12">(</span><span class="c9">i</span><span class="c12">+</span><span class="c51">1</span><span class="c12">)</span><span class="c10"> </span><span class="c12">%</span><span class="c10"> </span><span class="c51">2</span><span class="c10"> </span><span class="c46">==</span><span class="c10"> </span><span class="c51">0</span><span class="c10"> </span><span class="c3">{</span>

<span class="c10">           
</span><span class="c0">write!</span><span class="c12">(&</span><span class="c52">mut</span><span class="c10"> </span><span class="c9">new\_file</span><span class="c12">,"</span><span class="c48"> </span><span class="c3">");</span>

<span class="c10">        </span><span class="c3">}</span>

<span class="c10">    </span><span class="c3">}</span>

<span class="c3">}</span>

<span class="c3"></span>

<span class="c6"></span>

<span class="c6"></span>

<span class="c29"></span>

# <span class="c29">Chapter 4: CONCLUSION</span>

<span class="c6">Designing an 8 bit CPU was a choice I took so that the
architecture becomes easier to understand. Although a bit different than
how it's shown on slides, the computer has been implemented and for that
understanding of computer organization and architecture was necessary.
</span>

<span class="c6">Since the whole computer was built in Logisim. Logisim
needs to be installed on the device and the computer’s CIRC file needs
to be loaded. In any text editor program can be written, and then
assembler can assemble it into a format that can be loaded in Logisim.
On Logisim click on RAM and then open the assembled file. Once the
master clock is activated the program will run. </span>

<span class="c6"></span>

<span class="c6"></span>
