2402202409:53
tags: 
# Session 1 notes Proofs, Arguments, ZK

Verifiable Computing: Cryptographic protocols (IP and arguments) that enables a prover to provide to verifier a guarantee that he performed a requested computation correctly.

### Proof system
A proof system is a procedure that decides if a proof is convincing (valid) or not for a given statement. 
Properties that we want in a proof system:
- **Completeness**: Any true statement should have a convincing proof of its validity
- **Soundness**: No false statement should have a convincing proof
- Verification should be efficient, meaning that any proof can be **checked quickly** 
- Proving should be efficient as well, meaning that a convincing proof should be **easy to find**.

Traditionally, a mathematical proof is something that can be written and checked line-by-line to make sure it's correct. The traditional notion of proofs is captured by the complexity class **NP** (contains all problem which the correct answer is either YES or NO).

However we are now also interested in more exotic forms of proofs
## Chapter 1
### Interactive Proofs
An interactive proof is a proof where an untrusted prover is trying to convince a verifier that his proof is valid for a certain statement.
The difference between more traditional proofs is that the verifier is able to ask the prover some random "challenges" about his proofs that must hold if the proof is valid.
The prover does not know the challenges before submitting his proofs.
As an analogy, we could think of a mathematician trying to convince another one, the latter asking questions and challenging him!

### Multi Prover Interactive Proofs
An MIP is like an IP except that there are multiple provers, and they are assumed to not share informations between each other.

### Probabilistically Checkable Proofs
In a PCP, the proof is static like traditional proofs, but the verifier is allowed to read only a small number of (possibly random) characters of the proof.

### Arguments
Arguments are like IP, but they enable the existence of proofs of "incorrect" statements, so long as these proofs require exorbitant computational power.
Arguments make use of cryptography, so a cheating prover would have to break a very difficult problem to cheat.

## Chapter 2
### Reed-Solomon Fingerprinting
The Reed-Solomon Fingerprinting helps to transform a vector (for example a large file, or a matrix) into an unique fingerprint.

This is useful in multiple occasions, for example if we want to compare two very large file, we could both compute the fingerprint locally, query a random point of this fingerprint and send it to each other to make sure we have the same file, without actually transferring the file.

The way it works is something like this:
#### Parameters:
$a=(a_1,...,a_n)$: vector of size $n$. 
$\forall a_i \in a; a_i \in \{0,...,m\}$ 
$p$ a prime number where $p\geq max\{m,n^2\}$. We need $p\geq n^2$ for probabilistic reasons.
Every operation will be done $\bmod p$ 
For each $r\in \mathbb{F_p}$, define $h_r(a)=\sum{^n_{i=1}} a_i*r^{i-1}$.  
#### Details
We choose a random $r$. We then compute $h_r(a)$. This is the fingerprint of $a$ for $r$. 
The intuitive thing to understand is that this fingerprint is actually converting our vector into a polynomial of degree $n-1$.
$p_a(x)=a_1*x^0+a_2*x^1+...+a_n*x^{n-1}$. We then choose a random $r$ and compute $p_a(r)$.

If we would have two different vectors, even with only one small difference, the polynomial would be different, so it would very unlikely that we have the same result for a *random* $r$. 

We can think of this of extending our vector to make errors way more visible!

Also the fact that $r$ is random and unknown is very important to avoid making it possible to build a vector that would match for $r$.
#### Note 
We say that $p_a(r)$ is a random entry in the **error corrected encoding** of the vector $a$.

### Freivalds' Algorithm
#### Parameters
$A, B$ two $n\times n$ matrices.
$p$ a prime number where $p>n^2$.
#### Details
$A\cdot B$ is can be very expensive to compute. Let's say we are given a matrix $C$, supposed to be the result of $A\cdot B$. How to verify this in a more efficient way than compute $A\cdot B$ ?

First, choose a random $r\in \mathbb{F_p}$, and let $x=(1,r,r^2,...,r^{n-1})$. 
Compute $y=Cx$ and $z=A\cdot Bx$. Then compare $y$ and $z$.

We can observe that $(Cx)_i$ is actually $p_c(r)$, the Reed-Solomon fingerprint of $C_i$. Same goes for $(A\cdot B\cdot x)_i$. So we are actually comparing fingerprints!

---
## References
1. [Proofs,Arguments, and Zero-Knowledge](https://people.cs.georgetown.edu/jthaler/ProofsArgsAndZK.pdf) 