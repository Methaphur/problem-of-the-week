---
layout: post
permalink: problems/problem6
permalink_name: Problem 6
date: 2025-01-27
title: Beautiful String Pairs
---







# Problem Of The Week 4: Beautiful String Pairs

## Problem Statement

Given a string $t$ of length $m$, consisting of lowercase English letters, it is desired to split $t$ into parts. A pair of strings $(x, y)$ is defined as **beautiful** with respect to $t$ if and only if there exists a sequence of strings $a_1, a_2, \ldots, a_k$ such that:

$$
t = a_1 + a_2 + \cdots + a_k
$$

where $+$ denotes string concatenation. For each $1 \leq i \leq k$, at least one of the following conditions must hold: 

$$
a_i = x \quad \text{or} \quad a_i = y
$$

You are given another string $s$ of length $n$, consisting of lowercase English letters. For each $1 \leq i < n$, determine whether the pair of strings 

$$
(x, y) = (s_1 s_2 \cdots s_i, s_{i+1} s_{i+2} \cdots s_n)
$$

is beautiful with respect to $t$.
(The string $s$ is made up of the strings $s_i$, where $i$ goes from $1$ to $n$, and each $s_i$ contains one lowercase English letter.)

---

## Input Format

- A string $t$ of length $m$ consisting of lowercase English letters.
- A string $s$ of length $n$ consisting of lowercase English letters.
	  (The string $s$ is made up of the strings $s_i$, where $i$ goes from $1$ to $n$, and each $s_i$ contains one lowercase English letter.)

---

## Output Format

For each $1 \leq i < n$, output "YES" if the pair 

$$
(x, y) = (s_1 s_2 \cdots s_i, s_{i+1} s_{i+2} \cdots s_n)
$$

is beautiful with respect to $t$; otherwise, output "NO".

---

## Constraints

- $1 \leq m, n \leq 1000$
- $t$ and $s$ consist of only lowercase English letters.

---

## Example

### Input:
t = "ababab"
s = "abab"


### Output:

NO 
YES 
NO

---

## Explanation

- For $i = 1$:
  - $x = "a"$, $y = "bab"$.
  - $t$ cannot be split into parts where each part is either $x$ or $y$.
  - **Output:** NO

- For $i = 2$:
  - $x = "ab"$, $y = "ab"$.
  - $t$ can be split into 

$$
t = ab + ab + ab
$$

  where each part matches $x$ or $y$.
  - **Output:** YES

- For $i = 3$:
  - $x = "aba"$, $y = "b"$.
  - $t$ cannot be split into parts where each part is either $x$ or $y$.
  - **Output:** NO

---

## Objective

Write a program to determine for each $1 \leq i < n$ whether the pair 

$$
(x, y) = (s_1 s_2 \cdots s_i, s_{i+1} s_{i+2} \cdots s_n)
$$

is beautiful with respect to $t$.

---

Good luck and happy coding!
