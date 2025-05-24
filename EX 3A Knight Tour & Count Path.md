# EX 3A Knight Tour & Count Path
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight

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

class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,targetpos, N):
     # add your code here
    dx = [2, 2, -2, -2, 1, 1, -1, -1]
    dy = [1, -1, 1, -1, 2, -2, 2, -2]
     
    queue = []
    queue.append(cell(knightpos[0], knightpos[1], 0))
    visited = [[False for i in range(N + 1)]
                      for j in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True
    while(len(queue) > 0):
         
        t = queue[0]
        queue.pop(0)
        if(t.x == targetpos[0] and
           t.y == targetpos[1]):
            return t.dist
             
        # iterate for all reachable states
        for i in range(8):
             
            x = t.x + dx[i]
            y = t.y + dy[i]
             
            if(isInside(x, y, N) and not visited[x][y]):
                visited[x][y] = True
                queue.append(cell(x, y, t.dist + 1))
     
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,targetpos, N))
```

## Output:
![Screenshot 2025-04-29 225423](https://github.com/user-attachments/assets/9e4acfb5-e3df-4cdf-96cd-6215d13e38de)

## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
