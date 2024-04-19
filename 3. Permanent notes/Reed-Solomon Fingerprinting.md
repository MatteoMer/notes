2402202411:53
tags: 
# Reed-Solomon Fingerprinting

The Reed-Solomon Fingerprinting helps to transform a vector (for example a large file, or a matrix) into an unique fingerprint.

This is useful in multiple occasions, for example if we want to compare two very large file, we could both compute the fingerprint locally, query a random point of this fingerprint and send it to each other to make sure we have the same file, without actually transferring the file.

The way it works is something like this:
#### Parameters:
$a=(a_1,...,a_n)$: vector of size $n$. 
$\forall a_i \in a; a_i \in \{0,...,m\}$ 
$p$ a [[Prime numbers|prime number]] where $p\geq max\{m,n^2\}$. We need $p\geq n^2$ for probabilistic reasons.
Every operation will be done $\bmod p$ 
For each $r\in \mathbb{F_p}$, define $h_r(a)=\sum{^n_{i=1}} a_i*r^{i-1}$.  
#### Details
We choose a random $r$. We then compute $h_r(a)$. This is the fingerprint of $a$ for $r$. 
The intuitive thing to understand is that this fingerprint is actually converting our vector into a [[3. Permanent notes/Polynomials|polynomial]] of [[Degree of polynomial|degree]] $n-1$.
$p_a(x)=a_1*x^0+a_2*x^1+...+a_n*x^{n-1}$. We then choose a random $r$ and compute $p_a(r)$.

If we would have two different vectors, even with only one small difference, the polynomial would be different, so it would very unlikely that we have the same result for a *random* $r$. 

We can think of this of extending our vector to make errors way more visible!

Also the fact that $r$ is random and unknown is very important to avoid making it possible to build a vector that would match for $r$.
#### Note 
We say that $p_a(r)$ is a random entry in the **error corrected encoding** of the vector $a$.

---
## References
1. [[Proofs, Arguments, ZK Session 1 notes]]