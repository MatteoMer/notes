2109202311:29
tags: #archive 
# ECDLP

The discrete logarithm problem when used with Elliptic Curves is similar to the original one.
## Definition
Let $E$ an EC over $\mathbb{F_p}$ and $P,Q\in E(\mathbb{F_p})$.
The ECDLP is the problem on finding an integer $n$ such that $Q=nP$.
It appears difficult to find $n$ from $Q$ and $P$, that's why it seem difficult to solve the ECDLP.
## Note
Via analog to the original DLP, we note $n={log}_p(Q)$. We call it the elliptic discrete logarithm of $Q$ in respect to $P$.
## Double and add algorithm
We want to be able to compute efficiently $nP$, because if $n$ is large it can be very long.
We use similar method as square and multiply for DLP, but we'll call it double and add.
_Note that all operation must be computed $\bmod p$._
1. Set $Q=P$ and $R=\mathcal{O}$.
2. Loop while $n$ > 0:
	1. If $n\equiv1\bmod2$ set $R=R+Q$
	2. Set $Q=2Q$ and $n=\lfloor n/2\rfloor$
3. Return $R=nP$.
### Example
![[Pasted image 20230921115329.png]]
Note that $Q=2^iP$ because doubling $Q$ each time is equivalent to compute $Q=2^iP$.
### Remark
It's possible to optimize the speed of the double and add algorithm using the ternary expansion of $n$ but I don't know but about that yet.

---
## References
1. [[6. Archive/Elliptic Curve Discrete Logarithm Problem]]