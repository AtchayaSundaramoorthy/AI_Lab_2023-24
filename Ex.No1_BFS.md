# Ex No: 1 - Implementation of Breadth First Search

**Date:** 25-02-2025  
**Register Number:** 212222040021

## AIM:
To write a Python program to implement Breadth First Search (BFS).

## ALGORITHM:
1. Start the program.  
2. Create the graph using adjacency list representation.  
3. Define a function `bfs()` and initialize an empty list `visited` and an empty `queue`.  
4. Start the search with an initial node; add it to `visited` and `queue`.  
5. For each neighbor node, if it is not in `visited`, add it to both `visited` and `queue`.  
6. Create a loop to print the visited nodes.  
7. Call the `bfs()` function by passing the arguments `visited`, `graph`, and the starting node.  
8. Stop the program.

## PROGRAM:
```python
graph = {
    '5': ['3', '7'],
    '3': ['2', '4'],
    '7': ['8'],
    '2': [],
    '4': ['8'],
    '8': []
}

visited = []  
queue = []   

def bfs(visited, graph, node):  
    visited.append(node)
    queue.append(node)

    while queue:   
        m = queue.pop(0) 
        print(m, end=" ")   
        
        for neighbour in graph[m]:
            if neighbour not in visited:
                visited.append(neighbour)
                queue.append(neighbour)

print("Following is the Breadth-First Search:")
bfs(visited, graph, '5')
 
```

### Output:
![image](https://github.com/user-attachments/assets/881cbd76-6aec-4c04-816c-c63573a786f2)

### Result:
Thus, the Breadth First Search order was successfully obtained.
