# Lab 3: Asymptotic Analysis

This lab focuses on understanding and analyzing the asymptotic behavior of algorithms. We will explore concepts such as Big-O, Big-$\Theta$, and Big-$\Omega$ notations, and apply them to various algorithmic problems to determine their efficiency and scalability.

**Instructions:** To complete this lab, you may work in groups, but you must write your solutions yourself. Once you have completed the lab, push your changes to your forked repository.

## Problem 1

Suppose $T(n)$ is the worst case running time of an algorithm with input size $n$, and we know that $T(n)$ is $\mathcal{O}(n^3)$ and $\Omega(n^2)$. For each of the following statements, determine whether it must be true, must be false, or could be either true or false. Give a brief justification for each. 

1. $T(n)$ is $\mathcal{O}(n^2)$.
   
   Response: This statement would be either true or false. It would be true if it is $\Theta(n^2)$, however it would be false if it is $\Theta(n^3)$.
3. $T(n)$ is $\Theta(n^3)$.
   
   Response: Must be true. Since $T(n)$ takes at least $n^2$ steps ($\Omega(n^2)$), it automatically takes at least $n$ steps because $n^2>=n$ for all $n>=1$.
5. $T(n)$ is $\Omega(n)$.
   
   Response: This statement would be true. Since the lower bound is  $\Omega(n^2)$ and it takes $n^2$ steps while it is compeltely true that it can also take $n$ steps.
7. $T(n)$ is $\Theta(n^{1.5})$.
   
   Response: This statement would be false because the lower bound is $n^2$ i.e. $\Omega(n^2)$.
9. $T(n)$ is $\mathcal{O}(n)$.
    
   Response: This statement would be false because the lower bound is still $\Omega(n^2)$. Mathematically, it's impossible to run at least as faster as $\Omega(n^2)$ at $n$ steps.
11. $T(n)$ is $\Theta(n^2 \log n)$.
    
   Response: It would be true if $T(n) = n^2 \log n$, because $n^2 \log n$ falls strictly inside the allowed range between $n^2$ and $n^3$ (i.e., it satisfies both $O(n^3)$ and     $\Omega(n^2)$). However, it would be false if $T(n) = n^2$ or $T(n) = n^3$


## Problem 2
Consider the following algorithm where $f(A, i, j)$ is an unknown algorithm that takes as input an array $A$ and two indicies $i$ and $j$ and returns a number. 

```
Mystery Algorithm
Input: An array of int $A$ of length $n$.
Output: int sum
    n = |A|
    sum = 0
    for i = 1 to n:
        for j = 1 to n:
            sum += f(A, i, j)
```

Without knowing anything about $f$, what can we say about the running time of the Mystery Algorithm in terms of $n$? Justify your answer. 

Based on above algorithm,it must be $n^2$(counting two loops and ignoring constants) without calling the function itself. So, the runtime is $\Omega(n^2 \cdot T_f(n))$ and $O(n^2 \cdot T_f(n))$, which combine to form a tight bound $\Theta(n^2 \cdot T_f(n))$.
