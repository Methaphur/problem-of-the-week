---
layout : post
permalink :  solutions/solution1
permalink_name : /Solution 1
title : Solution Of The Week 1
---

Here's the problem statement [Problem 1]({{ site.baseurl }}/problems/problem1)

To solve this problem, we can use **Dynamic Programming** to calculate the minimum edit distance, also known as the **Levenshtein Distance**, between two strings.

Let’s define a 2D table `dp` where `dp[i][j]` represents the minimum number of operations required to transform the first `i` characters of `s1` into the first `j` characters of `s2`.

The three operations allowed are:
1. **Insert** a character: `dp[i][j-1] + 1`
2. **Delete** a character: `dp[i-1][j] + 1`
3. **Substitute** a character: `dp[i-1][j-1] + 1` if `s1[i-1] != s2[j-1]`

### Steps

1. **Initialization**:
   - `dp[i][0] = i` for all `i`, representing the cost of deleting all characters of `s1` to match an empty `s2`.
   - `dp[0][j] = j` for all `j`, representing the cost of inserting all characters of `s2` to match an empty `s1`.

2. **Filling the Table**:
   - For each `i` from `1` to `len(s1)` and each `j` from `1` to `len(s2)`, compute `dp[i][j]` as follows:
     - If `s1[i-1] == s2[j-1]`, then `dp[i][j] = dp[i-1][j-1]`
     - Otherwise, `dp[i][j] = min(dp[i-1][j-1] + 1, dp[i][j-1] + 1, dp[i-1][j] + 1)`

3. **Result**:
   - The answer is stored in `dp[len(s1)][len(s2)]`, representing the minimum edit distance.

### Code

```
def min_edit_distance(s1, s2):
    m, n = len(s1), len(s2)
    dp = [[0] * (n + 1) for _ in range(m + 1)]
    
    for i in range(m + 1):
        dp[i][0] = i
    for j in range(n + 1):
        dp[0][j] = j

    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if s1[i - 1] == s2[j - 1]:
                dp[i][j] = dp[i - 1][j - 1]
            else:
                dp[i][j] = min(dp[i - 1][j - 1] + 1, dp[i][j - 1] + 1, dp[i - 1][j] + 1)
    
    return dp[m][n]
```

### Submitted By: 
- IKnowWhyTheCagedBirdSings
- Sandipan Samanta
- Nehal Khosla
