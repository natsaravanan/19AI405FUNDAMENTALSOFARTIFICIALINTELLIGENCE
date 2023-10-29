### EX NO : 01
# <p align="center">Implement Depth First Search Traversal of a Graph</p> 
## Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.
## Theory:
<strong>Depth First Traversal </strong>(or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. 
Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.
## Procedure:
### Step 1: 
Initially, stack and visited arrays are empty.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/640b3c6f-3ac1-49a2-a955-68da9a71f446)
Queue and visited arrays are empty initially.</br>
Stack and visited arrays are empty initially.
### Step 2: 
Visit 0 and put its adjacent nodes which are not visited yet into the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/86dcf7d9-1f9d-49b0-a821-5976a6e77606)

 Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack</br>
 Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

### Step 3: 
Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/e6017942-08b1-4742-87ad-c97eb97bf985)

Visit node 1</br>
Visit node 1

### Step 4: 
Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c)

 Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack</br>
 Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

### Step 5: 
Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/20b76a05-5668-4da5-8189-e10fb1bb7238)

 Visit node 4</br>
 Visit node 4

### Step 6: 
Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/3b88f04a-7846-4f75-89b4-22bbd5b48e52)

Visit node 3</br>
Visit node 3</br>

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

## Algorithm:
<B><ol>
 <li>Construct a Graph with Nodes and Edges</li>
 <li>Depth First Search Uses Stack and Recursion</li>
 <li>Insert a START node to the STACK</li>
 <li>Find its Successors Or neighbors and Check whether the node is visited or not</li>
 <li>If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.</li>
</ol></B>

## Program:
Developed By : **Nithishkumar P**
</br>
Register No. : **212221230070**
```py
from collections import defaultdict

def dfs(graph, start, visited, path):
    path.append(start)
    visited[start] = True
    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)
            visited[neighbour] = True
    return path

graph = defaultdict(list)

n, e = map(int, input().split())

for i in range(e):
    u, v = map(str, input().split())
    graph[u].append(v)
    graph[v].append(u)

start = '0'          # 'A'
visited = defaultdict(bool)
path = []
traversed_path = dfs(graph, start, visited, path)
print(traversed_path)
```
## Output:
### Input 1:
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427017/fd92ded5-855f-4f15-b89d-03d878f60fff)
### Output 1:
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427017/9fc04859-3231-488a-8c8e-3528035d24f5)
### Input 2:
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427017/00934c20-7832-4e24-ae25-2a06ba1a13da)
### Output 2:
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/93427017/d08738f4-f5ea-4fce-8d0b-ab4a44e74a86)

## Result:
Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.
