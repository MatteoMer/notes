2709202318:55
tags: 
# Derive a polynomial from a set

One useful property of a polynomial of $deg(m)$ is that the polynomial is completely defined on $m+1$ points.
It means we can derive a polynomial from a set $S$ of points. $$S=\{(x_0,y_0),...,(x_n,y_n)|x_i\neq x_j\forall i,j \}$$
It means that polynomials have the property of being defined by a list of point $S: (x,P(x))\forall x\in R$

It's probably useful to represent a polynomial like this (maybe we can use ECC calculation with the points or represent an [[3. Permanent notes/Elliptic Curves|elliptic curve]] as a polynomial).

We will use [[Lagrange Interpolation]] to find the polynomial from the set of points $S$. 

---
## References
1. [[2. Literature notes/Polynomials]]