---
layout:     post
title:      Algorithm
subtitle:   Notes of Analysis and Design of Algorithms
date:       2020-03-11
author:     Eric
header-img: bg-202003142042.jpg
catalog: true
tags:
    - Algorithm
    - Class Notes
    - Notes
---



## Fundamentals of the Analysis of Algorithm Efficiency

### 0x01 Algorithm

* nonambiguity
* A sorting algorithm is called **stable** if it preserves the relative order of any two equal elements in its input. Generally speaking, algorithms that can exchange keys located far apart are not stable.
* An algorithm is said to be **in-place** if it does not require extra memory, except, possibly, for a few memory units.
* An graph with every pair of its vertices connected by an edge is called ***complete***.
* If all vertices of a path are distinct, the path is said to be **simple**.
* A graph is said to be **connected** if for every pair of its vertices u and v there is a path from u to v.
* A **cycle** is a path of a positive length that starts and ends at the same vertex and does not traverse the same edge more than once. A graph with no cycles is said to be **acyclic**.
* The number of edges in a tree is always one less than the number of its vertices.
* The **depth** of a vertex v is the length of the simple path from the root to v. The **height** of a tree is the length of the longest simple path from the root to a leaf.
* A binary tree with n nodes: $\lfloor log_2n\rfloor \le h \le n-1$
* 



### 0x02 Greatest Common Divisor

* Euclid's algorithm : gcd(m, n) = gcd(n, m mod n)  iteratively while n != 0
  gcd(m, 0) = m



### 0x03 Consecutive primes

* Sieve of Eratosthenes
* (2 through n) eliminate multiples of p that greater than or equal to  p*p

### 0x04 Binary Representation

* the number b of bits in the n’s binary representation : $b = \lfloor log_2n\rfloor + 1$

  ```c++
  count = 1;
  while(n > 1)
  {
      count++;
      n = n/2; //rounded down inherently
  }
  ```

  

### 0x05 Analysis of Nonrecursive Algorithm

* ![image-20200306215854078](http://q7266277k.bkt.clouddn.com/image-20200306215854078.png)

* $C_{op}$  :  basic operation   (the most time-consuming operation in the algorithm’s innermost loop)

* $O(g(n))$ is the set of all functions with a lower or same order of growth as $g(n)$ (to within a constant multiple, as $n$ goes to infinity)

  ![image-20200310133339074](http://q7266277k.bkt.clouddn.com/image-20200310133339074.png)

* $\Omega(g(n))$ is the set of all functions with a higher or same order of growth as $g(n)$ (to within a constant multiple, as $n$ goes to infinity)

  ![image-20200310133447766](http://q7266277k.bkt.clouddn.com/image-20200310133447766.png)

* $\Theta(g(n))$ is the set of all functions that have the same order of growth as $g(n)$ (to within a constant multiple, as  goes to infinity)

  ![image-20200310133412472](http://q7266277k.bkt.clouddn.com/image-20200310133412472.png)

* ![image-20200310133743390](http://q7266277k.bkt.clouddn.com/image-20200310133743390.png)

* $$
  L'hopital's\hspace{0.25cm} rule:\lim_{n\to\infty}\dfrac{t(n)}{g(n)}=\lim_{n\to \infty}\dfrac{t'(n)}{g'(n)}
  $$

* $$
  Stirling's\hspace{0.25cm}formula:\hspace{0.4cm}n!\approx\sqrt{2\pi n}(\dfrac{n}{e})^n \hspace{1cm}for\hspace{0.25cm}large\hspace{0.25cm}values\hspace{0.25cm}of\hspace{0.25cm}n
  $$



* |   Class   |     Name     |
  | :-------: | :----------: |
  |     1     |   constant   |
  | $log(n)$  | logarithmic  |
  |    $n$    |    linear    |
  | $nlog(n)$ | linearithmic |
  |   $n^2$   |  quadratic   |
  |   $n^3$   |    cubic     |
  |   $2^n$   | exponential  |
  |   $n!$    |  factorial   |



### 0x06 Tower of Hanoi

* Moving one disk as the algorithm's basic operation.

* $$
  M(n)=M(n-1)+1+M(n-1)\hspace{1cm} for\hspace{0.25cm}n>1\\
  M(1)=1\hspace{9cm}
  $$

### 0x07 Fibonacci Number

* 0, 1, 1, 2, 3, 5, 8, 13, 21, 34 ……
* $F(n)=F(n-1)+F(n-2)\hspace{0.8cm}for\hspace{0.25cm}n>1$
* $F(0)=0,\hspace{0.4cm}F(1)=1$
* **golden ratio:**  $\phi=(1+\sqrt5)/2$   $\hat\phi=-1/\phi$
* **solution:**  $F(n)=\dfrac{1}{\sqrt5}(\phi^n-\hat\phi^n)=\dfrac{1}{\sqrt5}\phi^n\hspace{0.25cm}rounded\;to\;the\;nearest\;integer$  

* $$
  \begin{bmatrix}
  F(n-1)&F(n)\\
  F(n)&F(n+1)
  \end{bmatrix}
  =
  \begin{bmatrix}
  0&1\\
  1&1
  \end{bmatrix}^n
  $$




## Brute Force and Exhaustive Search









