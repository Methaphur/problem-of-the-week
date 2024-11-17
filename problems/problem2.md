---
layout: post
permalink:  problems/problem2
permalink_name: /Problem 2
title: Problem Of The Week 2 
---

## Problem Statement: Engine Part Identification

You are a student at NISER working on an experimental research project involving a complex engine designed by engineers from IIT. This engine is critical for running a series of delicate chemical reactions, but as you begin testing, you realize that a crucial part might be missing. Unfortunately, the schematic of the engine is dense with part numbers and symbols, making it difficult to identify the missing piece.

The engine schematic (your puzzle input) consists of a visual representation of the engine. The schematic is filled with numbers and symbols, where each number represents a part number. To figure out which part is missing, you need to sum up all part numbers adjacent to a symbol. Numbers that are not adjacent (including diagonally) to any symbol are not part of the sum. Symbols can include characters like `*`, `#`, `+`, `$`, and `@`, while periods (`.`) should be ignored.

### Task

Calculate the sum of all part numbers that are adjacent to any symbol. This total will help you identify which part might be missing by comparing it to the expected total.

### Input

The input can be downloaded from [here]({{ site.baseurl }}/assets/files/problem2.txt).<br>
The input is a grid representing the engine schematic, where:
  - Each cell contains either a part number (a positive integer), a symbol (`*`, `#`, `+`, `$`, `@`), or a period (`.`).
  - Part numbers are considered integers adjacent to any symbol (directly or diagonally).

### Output

A single integer representing the sum of all part numbers adjacent to symbols.

### Example

**Input**
```plaintext
467..114..
...*......
..35..633.
......#...
617*......
.....+.58.
..592.....
......755.
...$.*....
.664.598..
```

**Output**
```plaintext
4361
```

**Explanation**

In this schematic:
- Two numbers (114 and 58) are not part numbers as they are not adjacent to any symbols.
- All other numbers adjacent to symbols contribute to the sum, resulting in a total of 4361.

### Solution
The solution to the problem can be found at [Solution 2]({{ site.baseurl }}/solutions/solution2).