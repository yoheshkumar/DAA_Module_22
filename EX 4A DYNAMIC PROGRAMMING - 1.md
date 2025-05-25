# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:

## AIM:
To find longest common subsequence using Dynamic Programming.


## Algorithm:

1. Create a 2D list dp of size `(m+1) x (n+1)` where `m` is the length of the first string and `n` is the length of the second string.
2. Each cell `dp[i][j]` will store the LCS of the substrings `x[0..i-1]` and `y[0..j-1]`.
3. Iterate through each character of the first and second strings using two nested loops.
4. If the characters match, append the matching character to the LCS found so far. If the characters do not match, select the longer LCS between the previous row or previous column.
5. Use the dp table to keep track of the longest subsequences as you traverse the strings.
6. The final LCS of the two strings will be in `dp[m][n]`.

## Program:
```
/*
Program to implement the longest common subsequence using Dynamic Programming

Developed by: YOHESH KUMAR R.M 
Register Number: 212222240118
*/

def lcs(x,y):
    m=len(x)
    n=len(y)
    dp=[["" for _ in range (n+1)]for _ in range(m+1)]
    for i in range(1,m+1):
        for j in range(1,n+1):
            if x[i-1]==y[j-1]:
                dp[i][j]=dp[i-1][j-1]+x[i-1]
            else: 
                dp[i][j] = dp[i - 1][j] if len(dp[i - 1][j]) > len(dp[i][j - 1]) else dp[i][j - 1]
    
    return dp[m][n]

str1=input()
str2=input()
print(f"{lcs(str1,str2)}")

```

## Output:

![image](https://github.com/user-attachments/assets/b9da6014-1be1-4899-96bc-e285e0f94383)

## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
