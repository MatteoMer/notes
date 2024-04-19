0204202410:24
tags: 
# Sum-Check Protocol

The sum-check protocol is a [[Interactive Proof System|proof system]] with the inputs:
- $g$ a $v$-variable [[3. Permanent notes/Polynomials|polynomial]] defined over $\mathbb{F}$.
The prover provides the following sum:
$$
H: \sum_{{b_1}\in\{0,1\}} \sum_{{b_2}\in\{0,1\}} \cdots \sum_{{b_v}\in\{0,1\}} g(b_1,b_2,...,b_v) 
$$
$H$ is the sum of all the [[Evaluation of a polynomial|evaluations of the polynomials]]
In the protocol, the prover gives $H$ to the verifier and want to convince him that $H$ is valid.
#### Remark 
We can use the protocol with any $B\subseteq\mathbb{F}$ s.t $\sum_{b\in B^v}g(b)$.
### Protocol
1. Prover sends a value $C$, claimed to be equal to $H$ for $g$.
2. Protocol does $v$ rounds, one for each variable of $g$.
3. **Round 1**
	1. The prover sends a polynomial $g_1$ claimed to be equal to $s_1$.
	   s1 can be computed as follow: $$s_1(X1)=\sum_{(x_2,\cdots,x_v)}g(X1,x2,\cdots,x_v)$$
	2. With the knowledge of $s1$ we can easily compute $H=s_1(0)+s_1(1)$.
	3. The verifier can check if $C=g_1(0)+g_1(1)$ to verify the claim
	4. If the prover is honest $g_1$ will have a degree of $deg_1(g)$ (the [[Degree of polynomial|degree]] of the first variable of $g$). It means we can describe $g_1$ in $deg_1(g)+1$ points and then use [[lagrange interpolation]].
	5. We can then easily check if $g1=s1$ using a [[Schwartz-Zippel Lemma|probabilistic check]] by taking a random point $r_1$ and check if $g_1(r1)=s_1(r1)$. 
	6. The difficult part for the verifier is that it's hard to compute $s_1$ by himself, the problem only being a factor of 2 smaller than the original one.
	7. Fortunately we can see that $s_1$ is a $v-1$-variate polynomial and the sum-check protocol is made for these kind of expressions. We can then recursively call the sum-check protocol, each call having a one less variable each time.
4. **Round 2...v**
	1. Protocol works in a recursive manner until $g_v(r_v)$ is equal to $g(r1,r2,\cdots,r_v)$ who can be easily computed by the verifier.
	2. After computing by himself, the verifier can unpack the computing and verify each step of the protocol
	3. In the last step, the verifier checks if $g_1=s_1$ and if it's valid, can accept the proof.
#### Remark
The verifier doesn't actually need to know $g$ to execute his part, but he must only be able to compute by himself $g(r)$ at the last round, he also needs to know the degrees of the $v$ variables of $g$. 

---
## References
1. [[Proofs, Arguments, ZKP Session 3]]