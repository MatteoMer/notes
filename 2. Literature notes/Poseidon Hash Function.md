0212202315:20
tags: #archive 
# Poseidon Hash Function

Poseidon is an arithmetization oriented hash function
## Arithmetization oriented hash function
Some AO Hash function:
- Poseidon
- Rescue
- Griffin
The difference between AO oriented hash functions and other is that they are not using boolean operation (for example XOR) because in a constraint system it will lead to a lot of constraint (and a bigger circuit)

AO functions don't need any bit operation, which make them "cheaper" in circuits
## Common design pattern for AO Hash function
It's using a substitution permutation network
1. Substitution
2. Permutation
3. Round constant
## Poseidon hash function
$f: \mathbb{F}^t_p \rightarrow\mathbb{F}^t_p$: meaning that if we want to map two elements, it will give two elements back. 

As parameters of the function we need:
- $p$ the prime field we'll be working in
- $t$ is the number of elements are processed each round
- $\alpha, gcd(\alpha, p-1)=1$ the exponent used in the S-Box step
- A matrice $M$ called the MDS, used in the diffusion step
- Some constants $c_1, c_2, ..., c_t$ that are changing in each round
### Steps
1. S-Box: $S(x_1, x_2)=(x_1^\alpha, x_2^\alpha)$
2. Diffusion: $M(x_1,x_2)=(a_1x_1+b_1x_2, a_2x_2+b_2x_2)$ (matrice addition)
3. Round constant: $C(x_1,x_2)=(x_1+c_1, x_2+c_2)$ 

We then do the same steps a certain amount of time!
When we do the S-Box to all elements, it's called a **full round** and when it's done on one element only it's called a **partial round**.
An implementation of Poseidon could do $n$ full rounds, then $k$ partial rounds and then $t$ full rounds again!
### Notes
- Most likely, the field will be a prime-order subgroup of the points of an EC where the curve is BLS12-381, BN254, or Ed25519 (as it has been made to work with these curves in mind).
- For these curves, it appears that the S-box where $\alpha=5$ is optimal

---
## References
1. [[Poseidon Hash Function - Danny Talk]]
2. https://www.poseidon-hash.info/
3. https://eprint.iacr.org/2019/458.pdf