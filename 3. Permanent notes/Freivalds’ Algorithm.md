2402202411:58
tags: 
# Freivalds’ Algorithm

It's an an efficient probabilistic [[Proofs systems|proof system]].
#### Parameters
$A, B$ two $n\times n$ matrices.
$p$ a [[Prime numbers|prime number]] where $p>n^2$.
#### Details
$A\cdot B$ is can be very expensive to compute. Let's say we are given a matrix $C$, supposed to be the result of $A\cdot B$. How to verify this in a more efficient way than compute $A\cdot B$ ?

First, choose a random $r\in \mathbb{F_p}$, and let $x=(1,r,r^2,...,r^{n-1})$. 
Compute $y=Cx$ and $z=A\cdot Bx$. Then compare $y$ and $z$.

We can observe that $(Cx)_i$ is actually $p_c(r)$, the [[Reed-Solomon Fingerprinting|Reed-Solomon fingerprint]] of $C_i$. Same goes for $(A\cdot B\cdot x)_i$. So we are actually comparing fingerprints!

---
## References
1. [[Proofs, Arguments, ZK Session 1 notes]]