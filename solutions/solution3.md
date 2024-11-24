---
layout : post
permalink :  solutions/solution3
permalink_name : /Solution 3
title : Solution Of Week 3
---

Here is the problem statement for [Problem 3]({{ site.baseurl }}/problems/problem3)


## Explanation of the Example
The buildings and connections can be represented as a graph. To minimize costs while connecting all buildings:
1. Use **Kruskal's Algorithm** to find the Minimum Spanning Tree (MST).
2. Start with the edge of the smallest cost:
   - Add edge `(3, 4, 1)` → Total cost = 1
   - Add edge `(2, 3, 2)` → Total cost = 3
   - Add edge `(1, 3, 3)` → Total cost = 6
   - Stop when all buildings are connected.
3. The total cost of the MST is **6**.

---

## Solution Approach

This is a classical *Minimum Spanning Tree (MST)* problem. The goal is to find a subset of edges that:
1. Connects all buildings (nodes) with the smallest total cost.
2. Ensures no cycles are formed.

### Algorithm: Kruskal's Algorithm
We use **Kruskal's Algorithm**, which efficiently builds the MST by:
1. **Sorting Edges**: Start with the smallest edge.
2. **Union-Find Data Structure**: Use a Union-Find (Disjoint Set Union) to check if adding an edge creates a cycle.
3. **Adding Edges**: Add edges to the MST until all nodes are connected.

If after processing all edges, not all nodes are connected, output `-1`.

# Union-Find (Disjoint Set Union)

The **Union-Find** data structure, also known as **Disjoint Set Union (DSU)**, is a powerful tool for solving connectivity problems. It efficiently keeps track of elements that are partitioned into disjoint (non-overlapping) sets and supports two key operations:

1. **Find**: Determines which set a particular element belongs to.
2. **Union**: Merges two sets into one.

---

## Implementation

```python
def find(parent, node):
    # Path compression for efficiency
    if parent[node] != node:
        parent[node] = find(parent, parent[node])
    return parent[node]

def union(parent, rank, u, v):
    # Union by rank
    root_u = find(parent, u)
    root_v = find(parent, v)
    if root_u != root_v:
        if rank[root_u] > rank[root_v]:
            parent[root_v] = root_u
        elif rank[root_u] < rank[root_v]:
            parent[root_u] = root_v
        else:
            parent[root_v] = root_u
            rank[root_u] += 1

def minimum_spanning_tree(n, edges):
    # Initialize Union-Find data structure
    parent = [i for i in range(n + 1)]
    rank = [0] * (n + 1)

    # Sort edges by weight
    edges.sort(key=lambda x: x[2])

    total_cost = 0
    edge_count = 0

    for u, v, w in edges:
        if find(parent, u) != find(parent, v):
            union(parent, rank, u, v)
            total_cost += w
            edge_count += 1
            # Stop early if we have connected all nodes
            if edge_count == n - 1:
                break

    # Check if all nodes are connected
    root_set = set(find(parent, i) for i in range(1, n + 1))
    if len(root_set) > 1:
        return -1
    return total_cost

# Input reading
n, m = map(int, input().split())
edges = []
for _ in range(m):
    u, v, w = map(int, input().split())
    edges.append((u, v, w))

# Output the result
result = minimum_spanning_tree(n, edges)
print(result)
```

# Solutions were submitted by : 

- PeithonKing 
- Sandipan Samanta

Kudos to all the participants who attempted this problem. Keep coding and learning! 

(Special mention to PeithonKing for solving it in Rust!)