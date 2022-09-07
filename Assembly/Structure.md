# Sections

## .data

In this section, data is declared and defined in the following format:
```asm
<variable name> <type>   <value>
```

Possible datatypes are:
```
--------------------------
| Type | Legnth  | Name  |
| db   | 8 bits  | Byte  |
| dw   | 16 bits | Word  |
| dd   | 32 bits | DWord |
| dq   | 64 bits | QWord |
--------------------------
```

This section can also contain constants, defined in the following format:
```
<constant name> equ   <value>
```

## .bss
`bss` stands for `Block Started by Symbol`. Uninitialized variables go here. Space for uninitialized variables is declared in this section in the following format:
```
<variable name> <type>   <number>
```

Possible datatypes are:
```
----------------------------
| Type   | Legnth  | Name  |
| resb   | 8 bits  | Byte  |
| resw   | 16 bits | Word  |
| resd   | 32 bits | DWord |
| resq   | 64 bits | QWord |
----------------------------
```

The variables in this section do not contain any values, the values will be assigned later at execution time. Memory places are not reserved at compile time but at execution time. The variables are initialized to zeroes, if there is not enough memory available for the `.bss` variables at execution time, the program will crash.

## .text
This section contains the program code.