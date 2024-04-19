2709202318:40
tags: 
# Euclidean division in polynomials

Euclidean division is defined for [[3. Permanent notes/Polynomials]].
It means that when there's $A,B\neq 0\in R[x]$ with $Lc(B)^-1\in R$, 
there exists two polynomials $Q,P\in R[x] \text{ s.t } A=Q\cdot B+P$. and $deg(P) < deg(B)$.
### Notation
We use the following notation:
$A \text{ div } B=Q$, $A\bmod B=P$.
If $A\bmod B=0$ we say that $A$ is divisible by $B$ and we note it $B|A$. 
$B$ is a factor of $A$.
## Algorithm
- With $A,B\neq 0\in R[x]$ and $Lc(B)^-1\in R$.
- $Q=0$
- $P=A$
- $d=deg(B)$
- $c=Lc(B)$
- while $deg(P)\geq d$:
	- $S=Lc(P)\cdot c^{-1}\cdot x^{deg(P)-d}$
	- $Q=Q+S$
	- $P=P-S\cdot B$
- return $(Q,P)$


---
## References
1. [[2. Literature notes/Polynomials]]