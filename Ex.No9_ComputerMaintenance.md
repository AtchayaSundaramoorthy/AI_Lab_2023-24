# Ex No: 9 - Logic Programming: Computer Maintenance Expert System

**Date:** 29-04-2025  
**Register Number:** 212222040021

## AIM:  
Write a Prolog program to build a computer maintenance expert system.

## ALGORITHM:  
1. Start the program.  
2. Write rules for each fault in the computer.  
3. If the system has printing problems, missing dots, and non-uniform printing, then the fault is printer head.  
4. If the system has no printing, missing dots, and spread ink, then the fault is ribbon.  
5. If the system has no printing, paper jam, and out of paper, then the fault is paper stuck in printer.  
6. Similarly define rules for all faults.  
7. Define facts for system problems.  
8. Find the fault by passing query to the system.

## PROGRAM:
```prolog
fault(printer_head) :-
    problem(not_printing),
    problem(missing_dots),
    problem(nonuniform_printing).

fault(ribbon) :-
    problem(not_printing),
    problem(missing_dots),
    problem(spread_ink).

fault(paper) :-
    problem(not_printing),
    problem(paper_jam),
    problem(out_of_paper).

fault(motherboard) :-
    problem(long_beep),
    problem(short_beep).

fault(hard_disc) :-
    problem(two_short_beeps),
    problem(blank_display).

problem(not_printing).
problem(missing_dots).
problem(spread_ink).
problem(two_short_beeps).
problem(blank_display).
```

### Output:
![image](https://github.com/user-attachments/assets/d59e225c-dd44-4f18-b3d0-d37f4e203b6a)

### Result:
Thus, the simple computer maintenance expert system was built successfully.
