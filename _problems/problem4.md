---
layout: post
permalink: problems/problem4
permalink_name: Problem 4
date: 2025-01-10
title: Alien Dictionary
---

## Problem Of The Week 4 : Alien Dictionary

In an alien language, surprisingly, they also use English lowercase letters, but possibly in a different order. The order of the alphabet is unknown to you. You are given a list of words from the alien language, sorted lexicographically by the rules of this new language. Derive the order of letters in this language.

### Input

- `words`: A list of strings representing the words in the alien language.

### Output

- A string representing the characters in the alien language, in the correct order.


**Sample Input:**
```
words = ["wrt", "wrf", "er", "ett", "rftt"]
```

**Output:**
```
"wertf"
```

### Constraints

1. You may assume all letters are in lowercase.
2. If the order is invalid, return an empty string.
3. There may be multiple valid order of letters, return any one of them.

### Hint

Think about how you can use graph theory to solve this problem. Consider constructing a graph where each node is a character and edges represent the order between characters. Then, perform a topological sort to determine the order of characters.

### Note

This problem is a standard coding question you see on LeetCode. You can find the original problem [here](https://leetcode.com/problems/alien-dictionary/).