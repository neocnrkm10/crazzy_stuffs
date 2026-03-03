# Comparing Two Prime-Checking Methods in Python

This program tests two different ways to check if a number is prime and shows which one is faster using a graph.  

---

## What is a Prime Number?

A **prime number** is a number greater than 1 that can only be divided evenly by **1** and itself.  
For example: 2, 3, 5, 7, 11 are all prime numbers.

---

## The Two Methods

### 1. Prime Check Using Combinations (`isprime`)

- This method uses **mathematical combinations**, which are a way to count the number of ways to choose items.  
- The formula used is:  
  \[
  \binom{n}{k} = \frac{n!}{k!(n-k)!}
  \]  
  where `!` means factorial (product of all numbers up to n).  
- To check if a number `p` is prime, it calculates `p choose i` for all numbers `i` from 1 to `p-1`, and checks if each value leaves a remainder of 0 when divided by `p`.  
- If all the remainders are 0, the number is prime; otherwise, it is not.

**Note:** This method is mathematically interesting but **very slow** for big numbers, because factorials grow extremely fast.

---

### 2. Prime Check Using Trial Division (`is_prime`)

- This method is much faster and more practical.  
- Steps:
  1. Numbers 0 and 1 are **not prime**.  
  2. Numbers 2 and 3 are **prime**.  
  3. Check if the number is divisible by 2 or 3. If yes, it is **not prime**.  
  4. For bigger numbers, check divisibility only up to the square root of the number.  
- If the number is not divisible by any of these, it is prime.  

This method is fast even for large numbers.

---

## What the Program Does

1. It tests numbers from **10 to 1000**, taking steps of 20 (i.e., 10, 30, 50…).  
2. It measures **how long each method takes** to check if a number is prime.  
3. It creates a **graph** using `matplotlib` showing the time taken by both methods.  

**Result:**  
- The red line shows the combination method (`isprime`).  
- The blue line shows the trial division method (`is_prime`).  
- You will see that the combination method takes **much more time** as numbers get bigger.

---

## Why This Is Useful

- It helps us **understand different algorithms** for the same task.  
- It shows that some methods (mathematical or fancy ones) may be **inefficient for computers**, while simple methods can be much faster.  
- It introduces **graphs to compare performance**, a key idea in computer science.

---

## Summary

- **Prime numbers** are important in math and computer science.  
- There are **many ways** to check if a number is prime.  
- **Trial division** is practical, **combination-based checking** is interesting but slow.  
- Measuring **time and plotting graphs** helps us visualize algorithm performance.