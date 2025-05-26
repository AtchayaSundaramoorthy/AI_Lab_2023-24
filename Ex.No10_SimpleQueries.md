# Ex No: 10 - Logic Programming: Simple Queries from Facts and Rules

**Date:** 29-04-2025  
**Register Number:** 212222040021

## AIM:  
To write a Prolog program to find the answer of a query.

## ALGORITHM:  
1. Start the program  
2. Convert the sentence into First Order Logic (FOL)  
3. Convert the sentence into Horn clause form  
4. Add rules and predicates in the program  
5. Pass the query to the program  
6. Prolog interpreter shows the output and returns answer  
7. Stop the program

## Task 1:  
Construct the FOL representation for the following sentences:  
1. John likes all kinds of food.  
2. Apples are food.  
3. Chicken is food.  
4. Sue eats everything Bill eats.  
5. Bill eats peanuts.  

Convert into clause form and prove that John likes apple by using Prolog.

### Program:
```prolog
food(apple).
food(vegetable).

eats(bill, peanuts).
eats(sue, X) :- eats(bill, X).

alive(bill).
```

### Output:
![image](https://github.com/user-attachments/assets/5a21172e-864e-45ca-8184-88d1b2aa4501)


### Task 2:
Consider the following facts and represent them in predicate form:  
1. Steve likes easy courses.  
2. Science courses are hard.  
3. All the courses in Have fun department are easy.  
4. BK301 is a Have fun department course.  

Convert the facts in predicate form to clauses and then prove by resolution:  
**“Steve likes BK301 course”**

### Program:
```prolog
likes(steve, X) :-
    easycourse(X).

hard(sciencecourse).

easycourse(X) :-
    course(X, dept(havefun)).

course(bk301, dept(havefun)).
```

### Output:
![image](https://github.com/user-attachments/assets/4d998175-a043-4cf8-942f-981fb6765555)

### Task 3:
Consider the statement:  
“This is a crime for an American to sell weapons to hostile nations. The Nano, enemy of America, has some missiles and its missiles were sold by Colonel West who is an American.”  

Convert to Clause form and prove West is criminal by using Prolog.

### Program:
```prolog
criminal(X) :- 
    american(X),
    weapon(Y),
    hostile(Z),
    sells(X, Y, Z).

weapon(Y) :- 
    missile(Y).

hostile(Z) :- 
    enemy(Z, america).  

sells(west, Y, nano) :- 
    missile(Y),
    owns(nano, Y).

missile(m).
owns(nano, m).
enemy(nano, america).
american(west).
```

### Output:
![image](https://github.com/user-attachments/assets/b0abca73-6685-4401-895d-29acb6f74ada)

### Result:
Thus, the Prolog programs were executed successfully and the answer to the queries was found.
