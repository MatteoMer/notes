0204202409:03
tags: 
# Lagrange Basis Polynomial

The Lagrange basis [[3. Permanent notes/Polynomials|polynomial]] can be described for each $i \in \{0,...,n-1\}$ over $\mathbb{F}_p$:
$$
δ_i(X)={\prod_{k=0,1,\cdots,n-1\space k\neq i}{(X-k)/(i-k)}}
$$
This polynomial is useful to act as an _indicator function_, because it maps $i$ to $1$ and every other input to $0$.
It's used to compute the [[Lagrange Interpolation]].

---
## References
1. [[Proofs, Args, ZK Session 2]]
