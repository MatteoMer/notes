0204202410:49
tags: 
# Reducing Multiple Polynomial Evaluations to One

It's often the case (for example, in certain uses of the [[Sum-Check Protocol]]) that you have a [[3. Permanent notes/Polynomials|polynomial]] $g$ composed of multiple other [[Multilinear Polynomial|multilinear polynomials]], such that, to compute $g$ at a single point, we need to compute some other polynomial $\tilde{\mathrm{W}}$ at multiple points. We can reduce the number of [[Evaluation of a polynomial|evaluation]] to one with a protocol.
### Protocol
Let's suppose $\tilde{\mathrm{W}}$ is a multivariate polynomial with $\log n$ variables over $\mathbb{F}$, and the verifier aims to evaluate $\tilde{\mathrm{W}}$ at two points $b,c \in \mathbb{F}^{\log n}$. 

We will reduce the cost of two verifications $\tilde{\mathrm{W}}(b)$ and $\tilde{\mathrm{W}}(c)$ to only one $\tilde{\mathrm{W}}(r)$ verification using a [[Schwartz-Zippel Lemma|probabilistic check]].

The protocol is a bit complex for me to understand now, but I understood that there's a line between $\tilde{\mathrm{W}}(b)$ and $\tilde{\mathrm{W}}(c)$, and we can restrict $\tilde{\mathrm{W}}$ to this line. 
The prover will send both points and the restricted polynomial, the verifier will check if a random point is indeed on the line, and if it's the case, will be convinced that the others are as well, but no idea why really 


---
## References
1. [[Proofs, Arguments, ZKP Session 3]]