---
layout: post
permalink:  problems/problem1
permalink_name: Problem 5
date: 2025-01-17
title: Bucket and Bucket 
---

## Problem of The Week 5: Bucket and Bucket

You are tasked with determining the number of actions required to measure an exact number of liters using two buckets of different sizes. The solution must follow a series of rules and constraints, given below

---

### Rules:

1. **Allowed Actions**:  
   - **Pouring**: Transfer water from one bucket to another until either:  
     a) the first bucket is empty, or  
     b) the second bucket is full.  
   - **Emptying**: Completely empty one bucket, doing nothing to the other.  
   - **Filling**: Completely fill one bucket, doing nothing to the other.

2. **Constraints on Final State**:  
   After any action, you **cannot** arrive at a state where:  
   - The starting bucket is empty, and  
   - The other bucket is full.

---

### Input:

1. **Bucket One Capacity (`size1`)**: The maximum capacity of bucket one (in liters).  
2. **Bucket Two Capacity (`size2`)**: The maximum capacity of bucket two (in liters).  
3. **Target Volume (`target`)**: The exact amount of water (in liters) to measure.  
4. **Starting Bucket**: The bucket that must be filled first, either "bucket one" or "bucket two".

---

### Output:

1. **Total Number of Actions (`actions`)**: The total number of actions required to measure the desired number of liters, including the first fill of the starting bucket.
2. **Final Target Bucket**: Which bucket (bucket one or bucket two) contains the desired number of liters at the end.
3. **Remaining Volume in the Other Bucket**: The number of liters left in the bucket that does not contain the target volume.

---

### Example:

- Bucket One: 7 liters  
- Bucket Two: 11 liters  
- Target: 6 liters  
- Starting Bucket: Bucket One  

Steps:  
1. Fill bucket one (7 liters).  
2. Pour bucket one into bucket two (bucket one: 0 liters, bucket two: 7 liters).  
3. Fill bucket one again (7 liters).  
4. Pour bucket one into bucket two until bucket two is full (bucket one: 3 liters, bucket two: 11 liters).  
5. Empty bucket two (bucket one: 3 liters, bucket two: 0 liters).  
6. Pour bucket one into bucket two (bucket one: 0 liters, bucket two: 3 liters).  
7. Fill bucket one again (7 liters).  
8. Pour bucket one into bucket two until bucket two contains 6 liters (bucket one: 4 liters, bucket two: 6 liters).

**Output**:  
- Total Actions: 8  
- Final Target Bucket: Bucket Two (6 liters)  
- Remaining Volume in Other Bucket: 4 liters  

---