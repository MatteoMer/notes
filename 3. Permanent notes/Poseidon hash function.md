0212202317:43
tags: 
# Poseidon hash function
Poseidon is an [[Arithmetization oriented hash function|AO hash function]] described as $f: \mathbb{F}^t_p \rightarrow\mathbb{F}^t_p$: meaning that if we want to map $t$ elements, it will give $t$ elements back. 

To make it work, you need few parameters:
- $p$ the [[Prime numbers|prime]] field we'll be working in
- $t$ is the number of elements are processed each round
- $\alpha, gcd(\alpha, p-1)=1$ the exponent used in the S-Box step
- A matrice $M$ called the MDS, used in the diffusion step
- Some constants $c_1, c_2, ..., c_t$ that are changing in each round
## Steps
1. S-Box: $S(x_1, x_2)=(x_1^\alpha, x_2^\alpha)$
2. Diffusion/Permutation: $M(x_1,x_2)=(a_1x_1+b_1x_2, a_2x_2+b_2x_2)$ (matrice addition)
3. Round constant: $C(x_1,x_2)=(x_1+c_1, x_2+c_2)$ 

We then apply the same steps a certain amount of time!
When we apply the S-Box to all elements, it's called a **full round** and when it's done on one element only it's called a **partial round**.

An implementation of Poseidon could do $n$ full rounds, then $k$ partial rounds and then $t$ full rounds again!
## Notes
- Most likely, the field will be a prime-order subgroup of the points of an [[3. Permanent notes/Elliptic Curves|EC]] where the curve is BLS12-381, BN254, or Ed25519 (as it has been made to work with these curves in mind).
- For these curves, it appears that the S-box where $\alpha=5$ is optimal

---
## References
1. [[2. Literature notes/Poseidon Hash Function]]