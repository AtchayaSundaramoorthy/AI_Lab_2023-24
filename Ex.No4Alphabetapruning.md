# Ex No: 4 - Implementation of Alpha Beta Pruning

**Date:** 18-03-2025  
**Register Number:** 212222040021

## AIM:
Write an Alpha-Beta Pruning algorithm to find the optimal value of the MAX player from the given game tree.

## STEPS:
1. Start the program.  
2. Initially assign MAX and MIN values as +∞ and -∞ respectively.  
3. Define the `minimax()` function using Alpha-Beta pruning.  
4. If maximum depth is reached (depth = 3), return the score value of the corresponding leaf node.  
5. During the MAX player’s turn, assign the alpha value by finding the maximum value through recursive calls.  
6. During the MIN player’s turn, assign the beta value by finding the minimum value through recursive calls.  
7. Specify the score values of the leaf nodes and call the `minimax()` function.  
8. Print the best value for the MAX player.  
9. Stop the program.

## PROGRAM:
```python
import math

INF = math.inf

def alpha_beta_pruning(depth, node_index, maximizing_player, values, alpha, beta, max_depth):
    if depth == max_depth:
        return values[node_index]

    if maximizing_player:
        max_eval = -INF
        for i in range(2):
            node_value = alpha_beta_pruning(depth + 1, node_index * 2 + i, False, values, alpha, beta, max_depth)
            max_eval = max(max_eval, node_value)
            alpha = max(alpha, node_value)
            
            if beta <= alpha:
                break  
        return max_eval
    else:
        min_eval = INF
        for i in range(2):
            node_value = alpha_beta_pruning(depth + 1, node_index * 2 + i, True, values, alpha, beta, max_depth)
            min_eval = min(min_eval, node_value)
            beta = min(beta, node_value)
            
            if beta <= alpha:
                break  
        return min_eval

if __name__ == "__main__":
    values = [3, 5, 6, 9, 1, 2, 0, -1]
    max_depth = int(math.log2(len(values))) 

    print("Optimal value:", alpha_beta_pruning(0, 0, True, values, -INF, INF, max_depth))

```

### Output:
![image](https://github.com/user-attachments/assets/afe81df9-14e4-41fe-a566-bbee76f89e16)


### Result:
Thus, the best score of the MAX player was successfully found using the Alpha-Beta Pruning algorithm.
