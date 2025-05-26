# Ex No: 11 -  Planning: Block World Problem  
### DATE: 15-04-2025                                                                           
### REGISTER NUMBER : 212222040021

### AIM: 
To find the sequence of plan for Block world problem using PDDL.

### Algorithm:
1. Start the program.  
2. Create a domain for Block world Problem.  
3. Define predicates: `clear`, `on-table`, `on`, `arm-empty`, and `holding`.  
4. Specify actions: `pickup`, `putdown`, `stack`, and `unstack`.  
5. In `pickup` action, the robot arm picks a block from the table.  
   Precondition: Block is on the table, clear, and the arm is empty.  
6. In `putdown` action, the robot arm places a block on the table.  
   Precondition: The robot arm is holding the block.  
7. In `unstack` action, the robot arm picks a block from another block.  
   Precondition: Block is on another block, clear, and arm is empty.  
8. In `stack` action, the robot arm places a block on another block.  
   Precondition: Robot arm is holding the block, and the under block is clear.  
9. Define a problem for the Block world problem.  
10. Obtain the plan for the given problem.

### Program (Domain):
```lisp
(define (domain blocksworld)
(:requirements :strips :equality)
(:predicates (clear ?x)
             (on-table ?x)
             (arm-empty)
             (holding ?x)
             (on ?x ?y))
(:action pickup
  :parameters (?ob)
  :precondition (and (clear ?ob) (on-table ?ob) (arm-empty))
  :effect (and (holding ?ob) (not (clear ?ob)) (not (on-table ?ob)) 
               (not (arm-empty))))
(:action putdown
  :parameters  (?ob)
  :precondition (and (holding ?ob))
  :effect (and (clear ?ob) (arm-empty) (on-table ?ob) 
               (not (holding ?ob))))
(:action stack
  :parameters  (?ob ?underob)
  :precondition (and  (clear ?underob) (holding ?ob))
  :effect (and (arm-empty) (clear ?ob) (on ?ob ?underob)
               (not (clear ?underob)) (not (holding ?ob))))
(:action unstack
  :parameters  (?ob ?underob)
  :precondition (and (on ?ob ?underob) (clear ?ob) (arm-empty))
  :effect (and (holding ?ob) (clear ?underob)
               (not (on ?ob ?underob)) (not (clear ?ob)) (not (arm-empty)))))
```

### Input (Problem):
```lisp
(define (problem pb1)
   (:domain blocksworld)
   (:objects a b)
   (:init (on-table a) (on-table b)  (clear a)  (clear b) (arm-empty))
   (:goal (and (on a b))))
```

### Output/Plan:
![image](https://github.com/user-attachments/assets/8132138e-ae5e-4b44-b7c9-6c6d0520ec1d)


### Result:
Thus, the plan was found for the initial and goal states of the block world problem.
