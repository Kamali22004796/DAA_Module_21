# EX 3D Pattern Matching
## DATE:
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.

## Algorithm:
```
1. Initialize lengths
2. Slide the pattern over the text
3.Check for match at each position
4.If full pattern matched
5.No match found
```

## Program:
```.
Developed by: Kamali E
Register Number:  212222110015
def BF(s1,s2):
    ##############  Add your code here #############
    m=len(s1)
    n=len(s2)
    for i in range(m-n+1):
        j=0
        while j<n and s1[i+j]==s2[j]:
            j+=1
        if j==n:
            return i
    return -1
    
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)

```

## Output:
![Screenshot 2025-04-29 230953](https://github.com/user-attachments/assets/66f2910a-edc6-40f0-ba0f-8c795ea6f223)

## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
