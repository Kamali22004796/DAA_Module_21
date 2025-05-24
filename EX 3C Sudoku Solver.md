# EX 3C Sudoku Solver
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.

## Algorithm:
```
1. Define `isPossible(row, col, val)` to check if placing a value at (row, col) is valid based on row, column, and 3×3 subgrid constraints.
2. Define `isEmpty()` to find and return the coordinates of the next empty cell; if none, the board is solved.
3. Define the recursive function `solve()` to fill the board.
4. If no empty cell is found, print the board and return True.
5. Otherwise, try digits 1 to 9 in the empty cell.
6. If a digit is valid, place it and call `solve()` recursively.
7. If recursion succeeds, return True; else, backtrack by resetting the cell.
8. If no digit fits, return False.
9. In main execution, call `solve()` to start solving and print the board when done.
```

## Program:
```
Developed by: Kamali E
Register Number:  212222110015

board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard():
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True
#####################  Add your code here #########################
def isEmpty():
    for r in range(9):
        for c in range(9):
            if board[r][c] == 0:
                return r, c
    return None


def solve():
    #####################  Add your code here #########################
    empty = isEmpty()
    if empty is None:
        printBoard()
        return True

    row, col = empty
    for guess in range(1, 10):
        if isPossible(row, col, guess):
            board[row][col] = guess
            if solve():
                return True
            board[row][col] = 0
    return False
solve()

```

## Output:
![Screenshot 2025-04-29 230511](https://github.com/user-attachments/assets/6f28bf86-8bc0-469b-9692-391b0afbe5f6)

## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
