2109202310:55
tags: #archive 
# Elliptic Curves in Finite Fields

To work with elliptic curve in cryptography we need to define the curve over $\mathbb{F_p}$ with $p$ a prime number.
We can define it pretty easily: $$E: Y^2 = X^3 + AX + B\text{ with A,B}\in\mathbb{F_p}\text{ and }4A^3+27B^2 \neq 0$$
And the points: $$E(\mathbb{F_p}) = \{{(x,y): x,y\in \mathbb{F_p}\text{ satisfy } y^2=x^3+Ax+B}\}\cup\mathcal{O} $$
Also we'll need to do all operation over $\mathbb{F_p}$.
## Check if an element is on the EC
We take an element $m\in\mathbb{F_p}$, and replace $x$ in the equation $\bmod p$ by $a$.
Then, if a solution exists, all the roots of the solution are a valid point.

Let $m\in\mathbb{F_p}$, $E=y^2=X^3+AX+B$.
If $y^2=m^3+A\cdot m+B$ holds, then all the roots of $y^2$ (for example $y_0, y_1$) are valid points 
With $(m,y_0), (m,y_1)\in E(\mathbb{F_p})$.
Else there's no valid point with $m$.
## Addition for EC in Finite fields
Addition works just like normal EC, but we need to be careful to do the operation over $\mathbb{F_p}$, for example in $\mathbb{F_{13}}$, if $P=(2,3)\text{ then }P'=(2,10)$ because the inverse of $3\bmod 13=10$.
## Note
Since the points on an EC forms a group, the points on an EC over a FF forms a finite group.
## Hasse's Theorem
The Hasse Theorem is used to get an approximation of how many points are on an EC defined over $F_P$.

Let $E$ an EC over $\mathbb{F_p}$. Then
$\#E(\mathbb{F_p})=p+1-t_p\text{ with }t_p\text{ satisfy }|t_p| \leq 2\sqrt p$.
$t_p$ is called the **trace of Frobenius** for $E/\mathbb{F_p}$. 

It means that the numbers of points over will be between $p+1-2\sqrt p$ and $p+1+2\sqrt p$.

---
## References
1. [[6. Archive/Elliptic Curves in Finite Fields|Elliptic Curves in Finite Fields]]