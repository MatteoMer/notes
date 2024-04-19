2509202315:13
tags: 
# Discrete Logarithm Problem

The discrete logarithm problem is a problem considered hard to solve.
## Definition 
Let $g$ a [[Primitive root theorem|primitive root]] of $\mathbb{F}_p$ and $h$ a non-zero element of $\mathbb{F}_p$. 
The Discrete Logarithm Problem is to find$$g^x\equiv h\pmod p$$
$x$ is called the **discrete logarithm** of $h$ to the base $g$ and is denoted by $log_g(h)$.
## Note
- If there's one solution to the [[congruence]], there's infinitely more. 
	If $x$ is a solution then $x+k(p-1) \forall k$ are solutions.
	In other words, we can say that $log_g(h)$ is defined by adding or subtract multiples of $(p-1)$. We can say that $log_g(h)$ is defined on $\bmod{p-1}$. 
	Sometimes we define DLP as the integer $x$ lying between $0$ and $p-2$ satisfying $g^x\equiv h\pmod p$.
- The discrete logarithm problem (DLP) exists in different versions for example using $\mathbb{F_p}$ or [[3. Permanent notes/Elliptic Curves|elliptic curves]]. You can check the [[General Definition of the DLP]] to have a wider view on the problem.

---
## References
1. [[An introduction to Mathematical Cryptography Chapter 2]]