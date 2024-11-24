---
layout: post
permalink: problems/problem3
permalink_name: /Problem 3
title: Problem Of The Week 3 (Solved)
---

## Problem Statement :  The NISER Campus Network

NISER is upgrading its campus network to provide seamless WiFi connectivity across all buildings. The goal is to connect `N` buildings in the campus with optical fiber cables. However, due to budget constraints, the total cost of the cables must be minimized.

Each pair of buildings can be connected by a direct cable of a certain length, which corresponds to the cost of laying that cable. The campus planning team has surveyed the buildings and provided a list of potential cable connections along with their costs. However, not all pairs of buildings need to be directly connected; the network only needs to be **fully connected**, meaning there should be a way to reach any building from any other building.

Your task is to help the planning team determine the minimum cost required to lay the cables such that all buildings are connected.

## Input Format

- The first line contains two integers, `N` (number of buildings) and `M` (number of possible cable connections)
- The next `M` lines each contain three integers: `u`, `v`, and `w`, where:
  - `u` and `v` are the buildings connected by the cable.
  - `w` is the cost of laying the cable between buildings `u` and `v`.

## Output Format

Output a single integer: the minimum cost to connect all the buildings. If it's not possible to connect all buildings, output `-1`.

## Constraints

- The buildings are numbered from `1` to `N`.
- Each cable connection is bidirectional.
- The network may not initially be connected (i.e., it's possible that some buildings cannot be connected with the given cables).

## Example

### Input
```
4 5
1 2 4
1 3 3
2 3 2
2 4 5
3 4 1
```

### Output
```
6
```


### Explanation
The optimal network connects the buildings as follows:
- Use the cable between buildings `3` and `4` (cost `1`).
- Use the cable between buildings `2` and `3` (cost `2`).
- Use the cable between buildings `1` and `3` (cost `3`).

The total cost is `1 + 2 + 3 = 6`.



Good Luck and Happy Coding

### Solution
The solution to the problem can be found at [Solution 3]({{ site.baseurl }}/solutions/solution3).
