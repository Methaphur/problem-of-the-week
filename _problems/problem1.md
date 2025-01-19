---
layout: post
permalink:  problems/problem1
permalink_name: Problem 1
date: 2024-10-28
title: String Transformation (Solved)
---

## Problem Of The Week 1 : String Transformation

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

### Submission
Think you've cracked it? [Submit your solutions here](https://docs.google.com/forms/d/e/1FAIpQLSefcxujcXFTQ9Z2u7__cf6RuFFzyJnMqSoRHTxFMM_v5pXrlA/viewform?usp=sf_link) and wait a few days to get it verified.

### Note 
- This technique, often called **Edit Distance** or **Levenshtein Distance**, is of particular interest in **bioinformatics**. Biologists use similar methods to measure differences between DNA, RNA, or protein sequences, helping to identify evolutionary relationships, mutations, and functional similarities. Such comparisons play a critical role in areas like gene editing, where understanding and calculating minimal sequence transformations can guide precise modifications to genetic material.

### Solution
The solution to the problem can be found at [Solution 1]({{ site.baseurl }}/solutions/solution1).