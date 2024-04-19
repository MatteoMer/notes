0204202410:44
tags: 
# Make real life problems work for the sum-check protocol

In general, when you have an input $x$ of length $n$ that you want to prove the validity of (for example the number of triangles in a graph); you can view this input as a function $f_\mathrm{X}$ mapping $\{0,1\}^{\log n}$ to some field $\mathbb{F}$. 
And then the [[multilinear extension]] of the function is used to create a [[Degree of polynomial|low-degree]] [[3. Permanent notes/Polynomials|polynomial]] $g$ where the desired answer equal the sum of all the [[Evaluation of a polynomial|evaluations]]. You can then use the [[Sum-Check Protocol]]. 

---
## References
1. [[Proofs, Arguments, ZKP Session 3]]