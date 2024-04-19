0204202409:33
tags: 
# Proofs, Arguments, ZKP Session 3

## Sum-Check Protocol
The sum-check protocol is a proof system with the inputs:
- $g$ a $v$-variable polynomial defined over $\mathbb{F}$.
The prover provides the following sum:
$$
H: \sum_{{b_1}\in\{0,1\}} \sum_{{b_2}\in\{0,1\}} \cdots \sum_{{b_v}\in\{0,1\}} g(b_1,b_2,...,b_v) 
$$
$H$ is the sum of all the evaluations of the polynomials
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
	4. If the prover is honest $g_1$ will have a degree of $deg_1(g)$ (the degree of the first variable of $g$). It means we can describe $g_1$ in $deg_1(g)+1$ points and then use [[lagrange interpolation]].
	5. We can then easily check if $g1=s1$ using a [[Schwartz-Zippel Lemma|probabilistic check]] by taking a random point $r_1$ and check if $g_1(r1)=s_1(r1)$. 
	6. The difficult part for the verifier is that it's hard to compute $s_1$ by himself, the problem only being a factor of 2 smaller than the original one.
	7. Fortunately we can see that $s_1$ is a $v-1$-variate polynomial and the sum-check protocol is made for these kind of expressions. We can then recursively call the sum-check protocol, each call having a one less variable each time.
4. **Round 2...v**
	1. Protocol works in a recursive manner until $g_v(r_v)$ is equal to $g(r1,r2,\cdots,r_v)$ who can be easily computed by the verifier.
	2. After computing by himself, the verifier can unpack the computing and verify each step of the protocol
	3. In the last step, the verifier checks if $g_1=s_1$ and if it's valid, can accept the proof.
#### Remark
The verifier doesn't actually need to know $g$ to execute his part, but he must only be able to compute by himself $g(r)$ at the last round, he also needs to know the degrees of the $v$ variables of $g$. 

### Double Efficient IP
We want to aim for IP where the prover runs in polynomial time and the verifier in linear time.
IP achieving this are called **double efficient**.
### How to take real life problems and make them work for the sum-check protocol?
In general, when you have an input $x$ of length $n$ that you want to prove the validity of (for example the number of triangles in a graph); you can view this input as a function $f_\mathrm{X}$ mapping $\{0,1\}^{\log n}$ to some field $\mathbb{F}$. 
And then the multilinear extension of the function is used to create a low-degree polynomial $g$ where the desired answer equal the sum of all the evaluations.
### Interesting routine in the sum-check protocol
It's often the case that the sum-check protocol is applied to a polynomial $g$ composed of multiple other multilinear polynomials, such that, to compute $g$ at a single point, we need to compute some other polynomial $\tilde{\mathrm{W}}$ at multiple points.

Let's suppose $\tilde{\mathrm{W}}$ is a multivariate polynomial with $\log n$ variables over $\mathbb{F}$, and the verifier aims to evaluate $\tilde{\mathrm{W}}$ at two points $b,c \in \mathbb{F}^{\log n}$. 

We will reduce the cost of two verifications $\tilde{\mathrm{W}}(b)$ and $\tilde{\mathrm{W}}(c)$ to only one $\tilde{\mathrm{W}}(r)$ verification using a [[Schwartz-Zippel Lemma|probabilistic check]].

The protocol is a bit complex for me to understand now, but I understood that there's a line between $\tilde{\mathrm{W}}(b)$ and $\tilde{\mathrm{W}}(c)$, and we can restrict $\tilde{\mathrm{W}}$ to this line. The prover will send both points and the restricted polynomial, the verifier will check if a random point is indeed on the line, and if it's the case, will be convinced that the others are as well, but no idea why really 


---
## References
1. [Proofs,Arguments, and Zero-Knowledge](https://people.cs.georgetown.edu/jthaler/ProofsArgsAndZK.pdf) 