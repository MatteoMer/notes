2109202313:55
tags: 
# Check if an element in on an [[Elliptic Curve over Finite Fields|EC over F_p]]
We take an element $m\in\mathbb{F_p}$, and replace $x$ in the equation $\bmod p$ by $a$.
Then, if a solution exists, all the roots of the solution are a valid point.

Let $m\in\mathbb{F_p}$, $E=y^2=X^3+AX+B$.
If $y^2=m^3+A\cdot m+B$ holds, then all the roots of $y^2$ (for example $y_0, y_1$) are valid points 
With $(m,y_0), (m,y_1)\in E(\mathbb{F_p})$.
Else there's no valid point with $m$.

We can compute how many points are in $E(\mathbb{F_p})$ using [[Hasse's Theorem]].

---
## References
1. [[2. Literature notes/Elliptic Curves in Finite Fields]]