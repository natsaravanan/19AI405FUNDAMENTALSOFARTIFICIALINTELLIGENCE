# EXP01-Implement-Depth-First-Search-Traversal-of-a-Graph
```
 NAME: HARSHAVARDHINI M
 REG NO: 212221240015
```
## AIM:
To Implement Depth First Search Traversal of a Graph using Python 3.

## THEORY:
Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking. Step 1: Initially, stack and visited arrays are empty.

![277147664-640b3c6f-3ac1-49a2-a955-68da9a71f446](https://github.com/Aashima02/AI01-Implement-Depth-First-Search-Traversal-of-a-Graph/assets/93427086/8155d09b-9c4f-429c-98b6-406cf90d5c37)

Queue and visited arrays are empty initially. Stack and visited arrays are empty initially. 

Step 2: Visit 0 and put its adjacent nodes which are not visited yet into the stack.
![277147583-86dcf7d9-1f9d-49b0-a821-5976a6e77606](https://github.com/Aashima02/AI01-Implement-Depth-First-Search-Traversal-of-a-Graph/assets/93427086/2bf01474-ae51-4127-b837-a6724e8c3922)
Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

Step 3: Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

![277147597-e6017942-08b1-4742-87ad-c97eb97bf985](https://github.com/Aashima02/AI01-Implement-Depth-First-Search-Traversal-of-a-Graph/assets/93427086/47b03a0d-18ac-4079-ae4d-cfec8d3bf9a6)

Visit node 1 Visit node 1

Step 4: Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.

![277147603-6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c](https://github.com/Aashima02/AI01-Implement-Depth-First-Search-Traversal-of-a-Graph/assets/93427086/117d9aae-631e-407f-a919-f53c155dd58a)

Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

Step 5: Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

![277147620-20b76a05-5668-4da5-8189-e10fb1bb7238](https://github.com/Aashima02/AI01-Implement-Depth-First-Search-Traversal-of-a-Graph/assets/93427086/7d5b4d77-912f-4164-9419-522df796703e)

Visit node 4 Visit node 4

Step 6: Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

![277147623-3b88f04a-7846-4f75-89b4-22bbd5b48e52](https://github.com/Aashima02/AI01-Implement-Depth-First-Search-Traversal-of-a-Graph/assets/93427086/daebc0c9-d9d7-4b59-ae0a-59085eab41bb)

Visit node 3 Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

## ALGORITHM:

1. Construct a Graph with Nodes and Edges

2. Depth First Search Uses Stack and Recursion

3. Insert a START node to the STACK

4. Find its Successors Or neighbors and Check whether the node is visited or not

5. If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.

## PROGRAM:
python
#import defaultdict
from collections import defaultdict
def dfs(graph,start,visited,path):
    path.append(start)
    visited[start]=True
    for neighbour in graph[start]:
        if visited[neighbour]==False:
            dfs(graph,neighbour,visited,path)
            visited[neighbour]=True
    return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
    u,v=map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)
#print(graph)
start='A'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)


### Sample Input:
![image](https://github.com/Aashima02/AI01-Implement-Depth-First-Search-Traversal-of-a-Graph/assets/93427086/fac182f3-6f35-4b25-b88e-5c33cebda4ed)

### Sample Output:
![image](https://github.com/Aashima02/AI01-Implement-Depth-First-Search-Traversal-of-a-Graph/assets/93427086/c06286a9-fe74-46cb-b5e0-118e4b46ad0f)


## RESULT:
Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.
