# Valid-Perfect-Square-DAY-5-CHALLENGE
class Solution {
    public boolean isPerfectSquare(int num) {
        long start = 1, end = num;
        while (start <= end) {
            long mid = ( start + end) / 2;
            if (mid * mid == num) return true; 
            if (mid * mid < num) {  
                start = mid + 1;
            } else {
                end = mid - 1; 
            }
        }
        return false;
    }
}



# Valid Perfect Square - DAY 5 CHALLENGE

This repository contains a Java solution to check whether a given number is a **perfect square** without using any built-in square root functions.

---

## Problem Statement

Given a positive integer `num`, return `true` if `num` is a perfect square, otherwise return `false`.

A **perfect square** is a number that can be expressed as the square of an integer (e.g., 1, 4, 9, 16, 25...).

---

## Solution Explanation

### Java Method

```java
public boolean isPerfectSquare(int num)
```

This method uses **binary search** to check whether `num` is a perfect square efficiently.

###  Step-by-Step Breakdown

#### 1. **Initialize Search Range**

We define our search space between 1 and `num`:

```java
long start = 1, end = num;
```

We use `long` instead of `int` to avoid integer overflow when squaring.

#### 2. **Binary Search Loop**

We keep narrowing down the search space:

```java
while (start <= end) {
    long mid = (start + end) / 2;
```

* If `mid * mid == num`, we’ve found our perfect square.
* If `mid * mid < num`, it means our square root must be higher → move `start` up.
* If `mid * mid > num`, it means our square root must be lower → move `end` down.

```java
    if (mid * mid == num) return true;
    if (mid * mid < num) {
        start = mid + 1;
    } else {
        end = mid - 1;
    }
```

#### 3. **Return the Result**

If we exhaust the search and find no integer whose square equals `num`, it's not a perfect square:

```java
return false;
```

---

##  Example

For `num = 16`:

* Binary search checks 8 → 4 → 2 → ... eventually finds `4 * 4 = 16`
* Returns `true`

For `num = 14`:

* No integer `x` such that `x * x = 14`
* Returns `false`

---

##  Time & Space Complexity

* **Time Complexity**: O(log n) — thanks to binary search
* **Space Complexity**: O(1) — no extra space used

---

##  Files

* `Solution.java`: Java implementation using binary search

---

This efficient approach avoids built-in functions and demonstrates a fundamental use of binary search for numerical problems.
