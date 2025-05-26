# Ex No: 12 - Planning: Monkey Banana Problem  

**Date:** 06-05-2025  
**Register Number:** 212222040021

## AIM: 
To find the sequence of plan for Monkey Banana problem using PDDL Editor.

## Algorithm:
1. Start the program.  
2. Create a domain for Monkey Banana Problem.  
3. Define predicates for the problem.  
4. Specify actions: `GO-TO`, `CLIMB`, `PUSH-BOX`, `GET-KNIFE`, `GRAB-BANANAS`.  
5. Define a problem instance for the Monkey Banana problem.  
6. Obtain the plan for the given problem.  
7. Stop the program.

## Program (Domain):
```pddl
(define (domain monkey)
  (:requirements :strips)
  (:constants monkey box knife bananas glass waterfountain)
  (:predicates 
    (location ?x)
    (on-floor)
    (at ?m ?x)
    (hasknife)
    (onbox ?x)
    (hasbananas)
    (hasglass)
    (haswater)
  )
  
  ;; movement and climbing
  (:action GO-TO
    :parameters (?x ?y)
    :precondition (and (location ?x) (location ?y) (on-floor) (at monkey ?y))
    :effect (and (at monkey ?x) (not (at monkey ?y)))
  )
  
  (:action CLIMB
    :parameters (?x)
    :precondition (and (location ?x) (at box ?x) (at monkey ?x))
    :effect (and (onbox ?x) (not (on-floor)))
  )
  
  (:action PUSH-BOX
    :parameters (?x ?y)
    :precondition (and (location ?x) (location ?y) (at box ?y) (at monkey ?y) (on-floor))
    :effect (and (at monkey ?x) (not (at monkey ?y)) (at box ?x) (not (at box ?y)))
  )
  
  ;; getting bananas
  (:action GET-KNIFE
    :parameters (?y)
    :precondition (and (location ?y) (at knife ?y) (at monkey ?y))
    :effect (and (hasknife) (not (at knife ?y)))
  )
  
  (:action GRAB-BANANAS
    :parameters (?y)
    :precondition (and (location ?y) (hasknife) (at bananas ?y) (onbox ?y))
    :effect (hasbananas)
  )
  
  ;; getting water
  (:action PICKGLASS
    :parameters (?y)
    :precondition (and (location ?y) (at glass ?y) (at monkey ?y))
    :effect (and (hasglass) (not (at glass ?y)))
  )
  
  (:action GETWATER
    :parameters (?y)
    :precondition (and (location ?y) (hasglass) (at waterfountain ?y) (at monkey ?y) (onbox ?y))
    :effect (haswater)
  )
)
```

## Input (Problem):
```pddl
 (define (problem pb1)
 (:domain monkey)
 (:objects p1 p2 p3 p4 bananas monkey box knife)
 (:init (location p1)
 (location p2)
 (location p3)
 (location p4)
 (at monkey p1)
 (on-floor)
 (at box p2)
 (at bananas p3)
 (at knife p4)
 )
 (:goal (and (hasbananas)))
)
```

## Output/Plan
![image](https://github.com/user-attachments/assets/d190b060-60af-450d-84da-ce37a6f356a3)

## Result:
Thus, the plan was found for the initial and goal states of the given problem.
