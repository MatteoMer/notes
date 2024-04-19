0104202411:32
tags: #archive 
# Session 2 Proofs, Args, ZK
### Lagrange Basis Polynomial and Interpolation
The Lagrange basis polynomial can be described for each $i \in \{0,...,n-1\}$ over $\mathbb{F}_p$:
$$
δ_i(X)={\prod_{k=0,1,\cdots,n-1\space k\neq i}{(X-k)/(i-k)}}
$$
This polynomial is useful to act as an _indicator function_, because it maps $i$ to $1$ and every other input to $0$.
It's used to compute the Lagrange Interpolation. For example if you want to find a polynomial $q_a$ such that $q_a(i)=a_{i+1}$ for $i \in \{0,...,n-1\}$, you can do:
$$
q_a(X)=\sum^{n-1}_{j=0} a_{j+1}\cdot δ_j(X)
$$ For each each $i$, every $X$ will be $0$ except if $X=i$, in this case, $q_a(X)=a_{i+1}$.

$q_a$ is often called the **univariate low degree extension of a** ($LDE(a)$).  For the vector $a$, $q_a$ creates an extension which is low degree. Such kind of functions are called **systematic** functions.

In coding-theory $a$ is called the message and the $LDE(a)$ the codeword.
### Interactive Proofs
An $k$-messages interactive proof system consists of:
- A ${0,1}^n$ domain, which represent a bit-message of size $n$.
- A probabilistic verifier algorithm $\mathcal{V}$ that runs in $poly(n)$ time
- A "honest" deterministic prover algorithm $\mathcal{P}$.
- Both $\mathcal{V}$ and $\mathcal{P}$ are given $x$ at the start
- $\mathcal{P}$ provides $y$, claiming that $f(x)=y$
- $\mathcal{P}$ and $\mathcal{V}$ exchange $k$ messages
- $\mathcal{V}$ needs to output if he accepts the claim or not
### Argument system
An argument system is an IP system where the soundness is required to hold against prover strategies that hold in polynomial time.
### Schwartz-Zippel Lemma
The Schwartz-Zippel Lemma implies that for two polynomials $p$ and $q$, over $\mathbb{F}$ , of degree $d$ at most, the probability that $p(x)=q(x)$ is $d/|\mathbb{F}|$. 
### Low Degree and multilinear extensions
#### Multilinear Polynomial
A multilinear polynomial is a multivariate polynomial with a degree of at most 1.
#### Multilinear extension
A function $v$-variate function $f$ over the domain $\{0,1\}^v$ have a multilinear extension polynomial (denoted $\tilde{f}$). 
It's similar to a LDE but has a much lower degree. (It has a degree $v$ at most).


---
## References
1. [Proofs,Arguments, and Zero-Knowledge](https://people.cs.georgetown.edu/jthaler/ProofsArgsAndZK.pdf) 