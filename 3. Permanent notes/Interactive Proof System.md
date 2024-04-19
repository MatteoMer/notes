0204202409:15
tags: 
# Interactive Proof System

An interactive proof system, is a [[Proofs systems|system]] that creates an [[Interactive Proof|interactive proof]].
It can be [[Mathematical Language|described mathematically]] like this:
An $k$-messages interactive proof system consists of:
- A ${0,1}^n$ domain, which represent a bit-message of size $n$.
- A probabilistic verifier algorithm $\mathcal{V}$ that runs in $poly(n)$ time
- A "honest" deterministic prover algorithm $\mathcal{P}$.
- Both $\mathcal{V}$ and $\mathcal{P}$ are given $x$ at the start
- $\mathcal{P}$ provides $y$, claiming that $f(x)=y$
- $\mathcal{P}$ and $\mathcal{V}$ exchange $k$ messages
- $\mathcal{V}$ needs to output if he accepts the claim or not

---
## References
1. [[Proofs, Args, ZK Session 2]]