---
layout: post
permalink:  problems/problem1
permalink_name: /Problem 1
title: Problem Of The Week 1
---

## Problem Statement: String Transformation (Edit Distance)

You are given two strings $s1$ and $s2$. Your task is to determine the **minimum number of operations** required to transform $s1$ into $s2$. You can use the following three operations:

1. **Insert** a character into the string.
2. **Delete** a character from the string.
3. **Substitute** one character in the string with another character.

Each operation has a cost of **1 unit**, and your goal is to achieve the transformation with the **minimum cost** possible.

### Input

- Two strings, $s1$ and $s2$, where:
    - $1 <= len(s1), len(s2) <= 500$
    - Both strings consist of only lowercase English letters.

### Output

- A single integer representing the minimum number of operations required to transform $s1$ into $s2$.


#### Example

```plaintext
Input: s1 = "kitten", s2 = "sitting"
Output: 3
```
**Explanation**
```plaintext
- kitten -> sitten (substitute 'k' with 's')
- sitten -> sittin (substitute 'e' with 'i')
- sittin -> sitting (insert 'g')
```

### Objective

Implement an efficient algorithm to calculate the minimum number of operations needed to convert $s1$ into $s2$ and return the cost.
