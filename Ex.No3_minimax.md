# Ex No: 3 - Implementation of Minimax Search

**Date:** 18-03-2025  
**Register Number:** 212222040021

## AIM:
Write a Mini-Max search algorithm to find the optimal value of the MAX Player from the given game tree.

## ALGORITHM:
1. Start the program.  
2. Import the `math` package.  
3. Specify the score values of the leaf nodes and find the depth of the binary tree using the number of leaf nodes.  
4. Define the `minimax()` function.  
5. If the maximum depth is reached, return the score value of the current leaf node.  
6. If it is the MAX player’s turn, find the maximum value by calling the `minimax()` function recursively.  
7. If it is the MIN player’s turn, find the minimum value by calling the `minimax()` function recursively.  
8. Call the `minimax()` function and print the optimum value of the MAX player.  
9. Stop the program.

## PROGRAM:
```python
import math

def minimax(curDepth, nodeIndex, maxTurn, scores, targetDepth):
    if curDepth == targetDepth:
        return scores[nodeIndex]

    if maxTurn:
        return max(
            minimax(curDepth + 1, nodeIndex * 2, False, scores, targetDepth),
            minimax(curDepth + 1, nodeIndex * 2 + 1, False, scores, targetDepth)
        )
    else:
        return min(
            minimax(curDepth + 1, nodeIndex * 2, True, scores, targetDepth),
            minimax(curDepth + 1, nodeIndex * 2 + 1, True, scores, targetDepth)
        )

scores = [3, 5, 2, 9, 12, 5, 23, 20]
treeDepth = int(math.log2(len(scores))) 

print("The optimal value is:", minimax(0, 0, True, scores, treeDepth))
```

### Output:
![image](https://github.com/user-attachments/assets/765cb41b-2844-46dc-9845-2c45f7f1c2f3)

### Result:
Thus, the optimum value of the MAX player was successfully found using the Minimax search algorithm.
