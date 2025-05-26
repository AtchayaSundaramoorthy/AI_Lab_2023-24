# Ex No: 6 - Logic Programming: Towers of Hanoi Problem

**Date:** 25-03-2025  
**Register Number:** 212222040021 

## AIM:
To write a logic program to solve the **Towers of Hanoi** problem using **SWI-PROLOG**.

## ALGORITHM:
1. **Start** the program.  
2. Write rules to solve the Towers of Hanoi problem in Prolog.  
   a) If there is only **one disk**, move the disk from X to Y.  
   b) If the number of disks is greater than 1:
   -  Move **N−1 disks** from source peg **X** to auxiliary peg **Z**.  
   -  Move the **Nth disk** from **X** to **Y**.  
   -  Move the **N−1 disks** from auxiliary peg **Z** to destination peg **Y**.  
4. Run the program to display the steps.  
5. **Stop** the program.

## PROGRAM:
```prolog
% Base Case
move(1, X, Y, _) :-
    write('Move disk from '), write(X), write(' to '), write(Y), nl.

% Recursive Case
move(N, X, Y, Z) :-
    N > 1,
    N1 is N - 1,
    move(N1, X, Z, Y),
    move(1, X, Y, _),
    move(N1, Z, Y, X).
```

### Output:
![image](https://github.com/user-attachments/assets/604c89d9-9c8c-4403-9ad1-c2bd0d1bb128)

### Result:
Thus, the solution to the Towers of Hanoi problem was successfully implemented using logic programming in SWI-PROLOG.
