2709202318:57
tags: 
# Lagrange Interpolation

The Lagrange interpolation is used to interpolate a [[3. Permanent notes/Polynomials|polynomial]] from a set of points.

Given a set $S$ of points, a polynomial $P$ of [[Degree of polynomial|degree]] $m$ with $P(x_i)=y_i$ $\forall$ pairs $(x_i,y_i)\in S$ is given by the algorithm:
![[Pasted image 20230927174727.png]]

It uses the [[Lagrange Basis Polynomial]] and for example, if you want to find a polynomial $q_a$ such that $q_a(i)=a_{i+1}$ for $i \in \{0,...,n-1\}$, you can do:
$$
q_a(X)=\sum^{n-1}_{j=0} a_{j+1}\cdot δ_j(X)
$$ For each each $i$, every $X$ will be $0$ except if $X=i$, in this case, $q_a(X)=a_{i+1}$.

$q_a$ is the [[univariate low degree extension]] of $a$

---
## References
1. [[2. Literature notes/Polynomials]]