---
layout: post
permalink: /CS141/challenge1
permalink_name: Challenge 1
title: Beginner Challenge 1
---

## Challenge Description

Write a program that prints the following star pattern:

```
*****
****
***
**
*
```



<details>
<style>
  code {
  font-family: MyFancyCustomFont, monospace;
  font-size: inherit; 
}
</style>
  <summary>Solution</summary>


  <pre><code>
  for i in range(5, 0, -1):
    print('*' * i)
  </code></pre>

To achieve this, we can use a `for` loop that iterates from 5 down to 1, decrementing by 1 each time. This means it starts at 5 and stops before reaching 0. And for each `for` loop iteration, the number of stars printed varies by `i`.

<br>
To recall, the `range` function in Python has the following syntax:

<pre><code>
range(starting_index, ending_index, step_value)
</code></pre>

<p>In this case, range(5, 0, -1) means:</p>
<ul>
  <li><code>starting_index</code> is 5</li>
  <li><code>ending_index</code> is 0 (exclusive)</li>
  <li><code>step_value</code> is -1 (increase by -1 each iteration)</li>
</ul>

Thus, the loop will generate the sequence: 5, 4, 3, 2, 1.
</details>


Good luck and happy coding!