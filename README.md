# VHDL
VHDL stands for **V**HSIC **H**ardware **D**escription **L**anguage.

VHSIC stands for **V**ery **H**igh **S**peed **I**ntegrated **C**ircuits.

VHDL is a programming language used for describing the behavior and structure of electronic systems. VHDL is widely used in the design, simulation, and verification of digital circuits, including field-programmable gate arrays (FPGAs) and application-specific integrated circuits (ASICs).

<img src="./pics/vhdl.png">

# WHY VHDL?
VHDL has the following advantages:-

+ It is industry standard and is IEEE Standard Language.
+ It is platform/vendor independent.
+It can be used to design and simulate digital circuits.
+ It supports hierarchical design
+ It is case insensitive
+ It is a concurrent language i.e. all lines of code execute at the same time. However, it also supports sequential statements.
+ Quick turn around time to market.

# How to write code in VHDL?

VHDL supports the follwing coding conventions:-
+ **DATAFLOW STYLE:-** Here, the code is written in a concurrent style where data flows from input to output after performing the necessary logical operations between input and output.
+ **BEHAVIORAL STYLE:-** Here, the code is written in hierarchical manner under processed statements and it describes the behaviour of the circuit with respect to it's truth table.
+ **STRUCTURAL STYLE:-** The code is written in hierarchical manner and different components of the circuit are described at first then they are reconnected to form the original larger circuit.
+ **MIXED STYLE:-** It is a combination of the above three styles.

# Components of VHDL code

<p align="center">
  <img src="./pics/components.png" height=300 width=400>
</p>

Components of VHDL code include the following:-
+ **Library & Package:-** It contains all essential logic and operations to develop the vhdl codes for example, addition, subtraction etc.
+ **Entity:-** It contains all input and output variables used in vhdl code.
+ **Architecture:-** It is the main body of of code where the user types the code to design the circuit.

# VHDL Codes

### Dataflow Style

+ Logical AND

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity andgate is
    Port ( a : in  STD_LOGIC;
           b : in  STD_LOGIC;
           y : out  STD_LOGIC);
end andgate;

architecture Behavioral of andgate is

begin

y <= a and b;

end Behavioral;
```

<p align="center">
  <img src="./pics/and1.png">
</p>