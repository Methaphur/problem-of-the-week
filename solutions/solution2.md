---
layout : post
permalink :  solutions/solution1
permalink_name : /Solution 1
title : Solution Of The Week 1
---

Here is the problem statement for [Problem 2]({{ site.baseurl }}/problems/problem2)

You are tasked with analyzing an engine schematic filled with part numbers (positive integers), symbols (`*`, `#`, `+`, `$`, `@`), and periods (`.`). To identify a missing part, calculate the sum of all part numbers adjacent (directly or diagonally) to any symbol. Numbers not adjacent to symbols are excluded. Find the sum of all part numbers adjacent to symbols in the given [input]({{ site.baseurl }}/assets/files/problem2.txt)

For the given problem input, the solution is **535078**

Here is how to solve it

### Step 1: Get the input

You can easily get a text file of the input using wget.

```bash
wget {{ site.baseurl }}/assets/files/problem2.txt
```

Or you can just copy paste it to a text file, nobody is going to judge you

### Step 2:  The Code

Here are some smaller tasks you can solve to get to the solution

1. **Reading Input**:
    - The input is read as a grid of strings.
    - You can use `open()` if you are using python.
2. **Identifying Symbols**:
    - The program identifies all cells that contain symbols (`*`, `#`, `+`, `$`, `@`) and collects all adjacent positions (directly or diagonally) into a set.
3. **Parsing Numbers**:
    - Numbers are parsed by identifying contiguous digits in each line.
4. **Checking Adjacency**:
    - For each parsed number, the program checks if any of its positions overlap with the symbol-adjacent positions.
5. **Calculating the Sum**:
    - Numbers adjacent to symbols are added to the total sum.

Here is a python solution for the problem

```py
with open('./input.txt', 'r') as f:
    puzzle_input = f.read()

lines = puzzle_input.split('\n')

# Identify the positions of symbols (non-numeric and non-dot characters)
symbol_adjacent = set()
for i, line in enumerate(lines):
    for j, char in enumerate(line):
        if not (char.isdigit() or char == '.'):
            # Add all adjacent positions of the symbol
            symbol_adjacent |= {(r, c) for r in range(i - 1, i + 2) for c in range(j - 1, j + 2)}

# Calculate the sum of numbers adjacent to symbols
part_num_sum = 0
for i, line in enumerate(lines):
    j = 0
    while j < len(line):
        if line[j].isdigit():
            # Parse the full number
            start = j
            while j < len(line) and line[j].isdigit():
                j += 1
            number = int(line[start:j])
            # Check if any position of the number is in symbol_adjacent
            if any((i, c) in symbol_adjacent for c in range(start, j)):
                part_num_sum += number
        else:
            j += 1

print(part_num_sum)

```

### Solutions were submitted by

Nobody got the correct answer this time. Submission ignored all symbols other than *, #, +, $, and @. But we are declaring you as winners as you were so close.

- Sandipan Samanta
- Prabhu and Pragya
- Nehal Khosla
