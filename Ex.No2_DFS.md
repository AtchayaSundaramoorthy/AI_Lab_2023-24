# Ex No: 2 - Implementation of Depth First Search

**Date:** 04-03-2025  
**Register Number:** 212222040021 

## AIM:
To write a Python program to implement Depth First Search (DFS).

## ALGORITHM:
1. Start the program.  
2. Create the graph using adjacency list representation.  
3. Define a function `dfs()` and initialize an empty set `visited`.  
4. Start the search with the initial node. If the node is not visited, print it.  
5. For each neighboring node, recursively invoke the `dfs()` function.  
6. Call the `dfs()` function by passing the arguments `visited`, `graph`, and the starting node.  
7. Stop the program.

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

visited = set()  # Set to keep track of visited nodes of graph.

def dfs(visited, graph, node):  # Function for DFS
    if node not in visited:
        print(node)  # Print visited node
        visited.add(node)
        for neighbour in graph[node]:
            dfs(visited, graph, neighbour)

# Driver Code
print("Following is the Depth-First Search")
dfs(visited, graph, '5')
```

### Output:
![image](https://github.com/user-attachments/assets/71a7aff7-a831-435c-ad07-c1a9ca07b1bf)


### Result:
Thus, the Depth First Search order was successfully obtained.
