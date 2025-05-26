# Ex No: 5 - Logic Programming: Factorial of a Number

**Date:** 08-04-2025  
**Register Number:** 212222040021

## AIM:
To write a logic program for finding the factorial of a given number using **SWI-PROLOG**.

## ALGORITHM:
1. **Start** the program.  
2. Write rules in **SWI-PROLOG** to find the factorial of a number.  
   - a) The factorial of 0 is 1 — written as `factorial(0, 1).`  
   - b) For numbers greater than 0, recursively call the factorial rule.  
3. Run the program and evaluate the query to obtain the result.  
4. **Stop** the program.

## PROGRAM:
```prolog
factorial(0, 1).

factorial(N, F) :-
    N > 0,
    N1 is N - 1,
    factorial(N1, F1),
    F is N * F1.
```

### Output:
![image](https://github.com/user-attachments/assets/b5b8d19c-6abf-4772-b461-75b0950ddf74)

### Result:
Thus, the factorial of the given number was successfully computed using logic programming in SWI-PROLOG.
