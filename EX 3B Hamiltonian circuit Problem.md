# EX 3B Hamiltonian Circuit Problem
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm:
```
1.Initialize a queue for BFS that stores (x, y, distance).
2.Track visited cells using a 2D array or a set.
3.Define the 8 possible knight moves
4.Start BFS from the initial position.
5.For each move, if the new position is valid and not visited, add it to the queue.
6.If the target is reached, return the number of moves taken.
7.If the queue is exhausted without reaching the target, return -1 (unreachable).
```

## Program:
```
Developed by: Kamali E
Register Number:  212222110015

def is_valid(v,pos,path,adj,N):
    ######################### Add your Code here ##########################
    if adj[path[pos-1]][v]==0:
        return False
    if v in path:
        return False
    return True
    
def hamUtil(adj,path,pos,N):
    if pos==N:
        return True
    for v in range(N):
        if is_valid(v,pos,path,adj,N):
            path[pos]=v
            if hamUtil(adj,path,pos+1,N):
                return True
            path[pos]=-1
            
def Hamiltonian_path(adj, N):
    path=[-1]*N
    path[0]=0

    if hamUtil(adj,path,1,N) == False:
        print ("Solution does not exist\n")
        return False

    # printSolution(path)
    return True
    
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```

## Output:
![Screenshot 2025-04-29 225741](https://github.com/user-attachments/assets/908da59b-ce72-45e4-b855-591730e8b205)

## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
