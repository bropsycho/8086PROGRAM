﷽

قٰلَ رَبِّيْ يَعْلَمُ الْقَوْلَ فِى السَّمَاۤءِ وَالْاَرْضِۖ وَهُوَ السَّمِيْعُ الْعَلِيْمُ

Surah Al-Anbiya – 4
Or Wohi Sun’nay Jan’nay Wala Hai
# INTEL8086
## BROPSYCHO

![N|Solid](https://i.imgur.com/mXrxBmI.jpg)


Problem: 



Write a procedure that finds the largest and the smallest
number from an array. The input in taken from the user and
stored in an array until zero (0) is entered. And the output
is shown in the console.
Hint: Use LEA to pass array in the procedure.

input output format: 
Sample Input:
12
5
6
9
0
Sample Output:
Smallest 5
Largest 12



## Features
* takes stack size as input 
* takes stack items as input in stack 
* prints maximum value from stack 
* prints minimum value from stack 

Code:
```ssh
INCLUDE 'EMU8086.INC'
org 100h
MOV BX,0
PRINT 'ENTER THE STACK SIZE: ' 
START: 
CALL SCAN_NUM
MOV VAR[BX], CX
ADD BX,2
MOV DX, CX
PRINTN ''
CMP DX,0
JE NEXT
LOOP START
NEXT: 
CALL ARRAY
MAIN: 
MOV AX,0 
PRINTN ''
PRINT 'LARGEST VALUE: '
MOV AX, DX
CALL PRINT_NUM
MOV CX,0
MOV AX,0 
PRINTN '' 
PRINT 'SMALLEST VALUE: ' 
MOV AX, MIN 
CALL PRINT_NUM
ret 
ARRAY PROC
MOV AX, BX
MOV BX,2
DIV BX
MOV CX, AX 
MOV BX,0 
MOV AX,1000 
L1: 
CMP VAR[BX],0
JE EXIT
CMP VAR[BX], DX
JGE MAXIMUM
CMP VAR[BX], AX
JL MINIMUM  
L2: 
ADD BX,2 
JMP L1     
MAXIMUM:
MOV CX, VAR[BX]
MOV DX, CX
MOV MAX, CX
JMP L2
MINIMUM:
MOV CX, VAR[BX]
MOV AX, CX
MOV MIN, CX
JMP L2
JMP L1
EXIT:
RET
JMP MAIN
ARRAY ENDP
VAR DW 10 DUP (?)
MAX DW ?
MIN DW ?
DEFINE_PRINT_NUM
DEFINE_PRINT_NUM_UNS
DEFINE_SCAN_NUM
END
```
## OUTPUT FORMAT: 
ENTER THE STACK SIZE: 5
12
5
6
9
0
LARGEST VALUE: 12
SMALLEST VALUE: 5

## THANK YOU 
Email: octalhacker@gmail.com
