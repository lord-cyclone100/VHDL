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

<!-- <p align="center">
  <img src="./pics/and1.png">
</p> -->
<br><br>
+ Logical OR

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity orgate is
    Port ( a : in  STD_LOGIC;
           b : in  STD_LOGIC;
           y : out  STD_LOGIC);
end orgate;

architecture Behavioral of orgate is

begin

y <= a or b;

end Behavioral;
```

<!-- <p align="center">
  <img src="./pics/or1.png">
</p> -->
<br><br>

+ Logical XOR

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity xorgate is
    Port ( a : in  STD_LOGIC;
           b : in  STD_LOGIC;
           y : out  STD_LOGIC);
end xorgate;

architecture Behavioral of xorgate is

begin

y <= a xor b;

end Behavioral;
```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ Half Adder

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity halfadder is
    Port ( a : in  STD_LOGIC;
           b : in  STD_LOGIC;
           s : out  STD_LOGIC;
           cout : out  STD_LOGIC);
end halfadder;

architecture Behavioral of halfadder is

begin

s <= a xor b;
cout <= a and b;

end Behavioral;
```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ Half Subtractor

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity halfsubtractor is
    Port ( a : in  STD_LOGIC;
           b : in  STD_LOGIC;
           d : out  STD_LOGIC;
           bout : out  STD_LOGIC);
end halfsubtractor;

architecture Behavioral of halfsubtractor is

begin

d <= a xor b;
bout <= (not a) and b;

end Behavioral;
```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ Full Adder

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity fulladder is
    Port ( a : in  STD_LOGIC_VECTOR(2 downto 0);
           y : out  STD_LOGIC_VECTOR(1 downto 0));
end fulladder;

architecture Behavioral of fulladder is

begin

y(1) <= a(2) xor a(1) xor a(0);
y(0) <= (a(2) and a(1)) or ((a(2) xor a(1)) and a(0));

end Behavioral;
```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ Full Subtractor

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity fullsubtractor is
    Port ( a : in  STD_LOGIC_VECTOR(2 downto 0);
           y : out  STD_LOGIC_VECTOR(1 downto 0));
end fullsubtractor;

architecture Behavioral of fullsubtractor is

begin

y(1) <= a(2) xor a(1) xor a(0);
y(0) <= (a(2) and a(1)) or ((a(2) xor a(1)) and a(0));

end Behavioral;
```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ 2 X 1 Multiplexer

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity mux is
    Port ( a : in  STD_LOGIC_VECTOR (1 downto 0);
           s : in  STD_LOGIC;
           o : out  STD_LOGIC);
end mux;

architecture Behavioral of mux is

begin

o <= ((not s) and a(0))or(s and a(1));

end Behavioral;
```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ 4 X 1 Multiplexer

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity mux is
    Port ( a : in  STD_LOGIC_VECTOR (3 downto 0);
           s : in  STD_LOGIC_VECTOR(1 downto 0);
           o : out  STD_LOGIC);
end mux;

architecture Behavioral of mux is

begin

o <= ((not s(0)) and (not s(1)) and a(0)) or 
((not s(0)) and s(1) and a(1)) or 
((not s(0)) and (not s(1)) and a(2)) or
(s(0) and s(1) and a(3));

end Behavioral;
```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ 2 : 4 Decoder

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity decoder is
    Port ( a : in  STD_LOGIC_VECTOR (1 downto 0);
           o : out  STD_LOGIC_VECTOR (3 downto 0));
end decoder;

architecture Behavioral of decoder is

begin

o(0) <= ((not a(0)) and (not a(1)));
o(1) <= ((not a(0)) and a(1));
o(2) <= (a(0) and (not a(1)));
o(3) <= (a(0) and a(1));

end Behavioral;

```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ 3 : 8 Decoder

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity decoder is
    Port ( a : in  STD_LOGIC_VECTOR (2 downto 0);
           o : out  STD_LOGIC_VECTOR (7 downto 0));
end decoder;

architecture Behavioral of decoder is

begin

o(0) <= ((not a(0)) and (not a(1)) and (not a(2)));
o(1) <= ((not a(0)) and (not a(1)) and a(2));
o(2) <= ((not a(0)) and a(1) and (not a(2)));
o(3) <= ((not a(0)) and a(1) and a(2));
o(4) <= (a(0) and (not a(1)) and (not a(2)));
o(5) <= (a(0) and (not a(1)) and a(2));
o(6) <= (a(0) and a(1) and (not a(2)));
o(7) <= (a(0) and a(1) and a(2));

end Behavioral;

```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->

### Behavioral Style
+ Logical AND gate

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
	process(a,b)
	variable temp:STD_LOGIC:='0';
		begin
			if(a = '1' and b= '1')then
				temp := '1';
			else
				temp := '0';
		end if;
		y <= temp;
	end process;
end Behavioral;

```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ Logical OR gate

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity orgate is
    Port ( a : in  STD_LOGIC;
           b : in  STD_LOGIC;
           y : out  STD_LOGIC);
end orgate;

architecture Behavioral of orgate is

begin
	process(a,b)
	variable temp:STD_LOGIC:='0';
		begin
			if(a = '0' and b= '0')then
				temp := '0';
			else
				temp := '1';
		end if;
		y <= temp;
	end process;
end Behavioral;

```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ Logical XOR gate

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity xorgate is
    Port ( a : in  STD_LOGIC;
           b : in  STD_LOGIC;
           y : out  STD_LOGIC);
end xorgate;

architecture Behavioral of xorgate is

begin
	process(a,b)
	variable temp:STD_LOGIC:='0';
		begin
			if(a = b)then
				temp := '0';
			else
				temp := '1';
		end if;
		y <= temp;
	end process;
end Behavioral;

```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ 4 X 1 Multiplexer

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity multiplexer is
    Port ( i : in  STD_LOGIC_VECTOR(3 downto 0);
           s : in  STD_LOGIC_VECTOR(1 downto 0);
           y : out  STD_LOGIC);
end multiplexer;

architecture Behavioral of multiplexer is

begin
	process(s,i)
	variable temp:STD_LOGIC:='0';
		begin
			if(s = "00")then
				y <= i(0);
            elsif(s = "01")then
				y <= i(1);
            elsif(s = "10")then
				y <= i(2);
			else
				y <= i(3);
		end if;
	end process;
end Behavioral;

```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->
<br><br>
+ 3 : 8 ddecoder

**CODE:**
```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
use IEEE.STD_LOGIC_ARITH.ALL;
use IEEE.STD_LOGIC_UNSIGNED.ALL;

entity decoder is
    Port ( i : in  STD_LOGIC_VECTOR(3 downto 0);
           y : out  STD_LOGIC_VECTOR(1 downto 0));
end decoder;

architecture Behavioral of decoder is

begin
	process(i)
	variable temp:STD_LOGIC:='0';
		begin
			if(i = "000")then
				y <= "00000001";
            if(i = "001")then
				y <= "00000010";
            if(i = "010")then
				y <= "00000100";
            if(i = "011")then
				y <= "00001000";
            if(i = "100")then
				y <= "00010000";
            if(i = "101")then
				y <= "00100000";
            if(i = "110")then
				y <= "01000000";
			else
				y <= "10000000";
		end if;
	end process;
end Behavioral;

```

<!-- <p align="center">
  <img src="./pics/xor1.png">
</p> -->