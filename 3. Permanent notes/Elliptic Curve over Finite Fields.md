2109202313:41
tags: 
# Elliptic Curve over Finite Fields

To work with [[Elliptic Curves|elliptic curve]] in cryptography we need to define the curve over a finite field $\mathbb{F_p}$ with $p$ a prime number.
We can define it pretty easily: $$E: Y^2 = X^3 + AX + B\text{ with A,B}\in\mathbb{F_p}\text{ and }4A^3+27B^2 \neq 0$$
And the points: $$E(\mathbb{F_p}) = \{{(x,y): x,y\in \mathbb{F_p}\text{ satisfy } y^2=x^3+Ax+B}\}\cup\mathcal{O} $$
Also we'll need to do all operation over $\mathbb{F_p}$.
## Note
- Since the points on an EC forms a group, the points on an EC over a FF forms a finite group.

---
## References
1. [[2. Literature notes/Elliptic Curves in Finite Fields]]