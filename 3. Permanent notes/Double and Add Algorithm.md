2109202314:01
tags: 
# Double and Add Algorithm

We want to be able to compute efficiently $nP$ (to do [[Scalar Multiplication in EC]]), because if $n$ is large it can be very long.
We use similar method as square and multiply for DLP, but we'll call it double and add.
_Note that all operation must be computed $\bmod p$.

Let $P\in E(\mathbb{F_p})$.
1. Set $Q=P$ and $R=\mathcal{O}$.
2. Loop while $n$ > 0:
	1. If $n\equiv1\bmod2$ set $R=R+Q$
	2. Set $Q=2Q$ and $n=\lfloor n/2\rfloor$
3. Return $R=nP$.

Example: [[Double and Add Algorithm Example]]
### Remark
It's possible to optimize the speed of the double and add algorithm using the ternary expansion of $n$ but I don't know much about that yet.


---
## References
1. [[ECDLP]]