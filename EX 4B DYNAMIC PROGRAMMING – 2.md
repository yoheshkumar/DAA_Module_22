# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..

## Algorithm
1. Create a 2D table dp of size `(m+1) x (n+1)`, where `m` is the length of the first string and `n` is the length of the second string. Set all elements to `0` initially.
2. Track the maximum length of the common substring (`max`) and its ending position (`end`).
3. For each character pair (`x[i-1], y[j-1]`) in the two strings, if they match, update `dp[i][j]` to `dp[i-1][j-1] + 1`.
4. If this new length is greater than the current max, update max and end.
5. Use the recorded end and max values to slice the longest common substring from the original string.

## Program:
```
/*
Program to implement the longest common substring problem

Developed by: YOHESH KUMAR R.M
Register Number: 212222240118
*/

def lcs(x,y):
    m=len(x)
    n=len(y)
    max=0
    end=m
    dp=[[0 for i in range(n+1)] for j in range(m+1)]
    for i in range(1,m+1):
        for j in range(1,n+1):
            if x[i-1]==y[j-1]:
                dp[i][j]=dp[i-1][j-1]+1
                if dp[i][j]>max:
                    max=dp[i][j]
                    end=i
    return x[end-max:end]

s1=input()
s2=input()
print("The longest common substring is",(lcs(s1,s2)))

```

## Output:

![image](https://github.com/user-attachments/assets/aada1624-d79b-498c-bac8-d6e1806ced26)

## Result:
Thus the program was executed successfully for finding the longest common substring .
