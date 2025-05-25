# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm
1. If one of the strings is empty, the edit distance is the length of the other string (all insertions or deletions).
2. If the last characters of both strings match, no additional cost is needed for this position, so set count `=0`.
3. If they do not match, set count `=1` to account for the replacement cost.
4. Return the minimum of the following three operations:
   - Insertion: Edit distance after inserting the last character of `t` into `s`.
   - Deletion: Edit distance after deleting the last character of `s`.
   - Replacement: Edit distance after replacing the last character if the characters differ.
5. Return the minimum cost from the above operations, including the current count if applicable.


## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method

Developed by: YOHESH KUMAR R.M
Register Number: 212222240118
*/

def LD(s, t):
    if s=="":
        return len(t)
    if t=="":
        return len(s)
    if s[-1]==t[-1]:
        count=0
    else:
        count=1
    res=min([LD(s[:-1],t)+1,LD(s,t[:-1])+1,LD(s[:-1],t[:-1])+count])
    return res
    
str1=input()
str2=input()
print('No. of Operations required :',LD(str1,str2))

```

## Output:

![image](https://github.com/user-attachments/assets/98085c84-83c8-40d4-9aed-3f606611ef30)

## Result:
Thus the program was executed successfully for finding edit distance between two strings.
