# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.

## Algorithm

1. Create a 2D dp table of size `(n+1) x (n+1)` initialized to `-1` to store intermediate results for overlapping subproblems.
2. Use the `lps()` function to compute the LPS length by treating it as a Longest Common Subsequence (LCS) problem between the original string (`s1`) and its reverse (`s2`).
3. If the characters match, increment the length and move both pointers.
4. If the characters do not match, take the maximum length by either moving the first or the second pointer backward.
5. If the result for a given subproblem is already computed (i.e., `dp[n1][n2] != -1`), return the stored value to avoid redundant calculations.
6. Print the final LPS length once the recursive function returns the result.

## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it

Developed by: YOHESH KUMAR R.M
Register Number: 212222240118
*/

dp = [[-1 for i in range(1001)]for j in range(1001)]
def lps(s1, s2, n1, n2):
    if (n1 == 0 or n2 == 0):
        return 0
    if (dp[n1][n2] != -1):
        return dp[n1][n2]
    if (s1[n1 - 1] == s2[n2 - 1]):
        dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)
        return dp[n1][n2]
    else:
        dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))
        return dp[n1][n2]
        
seq = input()
n = len(seq)
s2 = seq
s2 = s2[::-1]
print(f"The length of the LPS is",lps(s2, seq, n, n))

```

## Output:

![image](https://github.com/user-attachments/assets/4fe2d055-9b39-4f07-9492-9213febbf50d)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
