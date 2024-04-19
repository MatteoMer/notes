f2109202314:00
tags: 
# Elliptic Curve Discrete Logarithm Problem

The [[discrete logarithm problem]] when used with Elliptic Curves is similar to the original one.
## Definition
Let $E$ an EC over $\mathbb{F_p}$ and $P,Q\in E(\mathbb{F_p})$.
The ECDLP is the problem on finding an integer $n$ such that $Q=nP$.
It appears difficult to find $n$ from $Q$ and $P$, that's why it seem difficult to solve the ECDLP.
## Note
- Via analog to the original DLP, we note $n={log}_p(Q)$. We call it the elliptic discrete logarithm of $Q$ in respect to $P$.
- We use the [[Double and Add Algorithm]] to compute efficiently $nP$.

---
## References
1. [[ECDLP]]