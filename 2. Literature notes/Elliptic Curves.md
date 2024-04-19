1909202318:33
tags: 
# Elliptic Curves
An elliptic curve is the set of solutions of to Weierstrass equation of the form $$E: Y^2=A^3+AX+B$$
together with a point $\mathcal{O}$ where $A$ and $B$ must satisfy $4A^3+27B^2\neq0$.
The points on $E$ forms an abelian group.
## Point addition
In an elliptic when we want to add two points $P$ and $Q$ to get a third point we need to find the line that crosses $P$ and $Q$ and find the intersection $R$ of this line on $E$.

Then with $R=(a,b)$ the sum of $P$ and $Q$ is defined to be the reflection $R'=(a,-b)$.
![[Pasted image 20230919184229.png]]
We also need to acknowledge that $\mathcal{O}$ is the point of infinity and lies on every line.
## Remarks on point addition
- If we want to do $P+P$, we take $L$ as the tangent of $E$ at $P$.
- If we want to do $P+P'$, we will not find any intersection on the curve. That's where the point of infinity comes useful. We can then say that $P+P'=\mathcal{O}$. 
### Point of infinity
The point of infinity is a point that does not exists on the XY-plane but we will pretend it lies on every vertical line.
- $P+P'=\mathcal{O}$ 
- $Q+P+\mathcal{O}=Q+P$ 
- $P+\mathcal{O}= P$ 
The point of infinity act like 0 in elliptic curves addition.

## Elliptic Curve Addition Algorithm
With $E$ an elliptic curve and let $P_1,P_2 \in E$ two points.
a. If $P_1=\mathcal{O}$ then $P_1+P_2=P_2$
b. If $P_2=\mathcal{O}$ then $P_1+P_2=P_1$
c. Write $P_1$ as $x_1,y1$ and $P_2$ as $x_2,y_2$
d. If $x_1=x_2$ and $y_1=-y_2$ then $P_1+P_2=\mathcal{O}$ 
e. Else define $\lambda$ by: $$
\lambda=
\begin{cases}
\frac {y_2-y_1}{x_2-x_1}& \text{if } P_1 \neq P_2\\
\frac {3x_1^2+A}{2y_1}& \text{if } P_1=P_2
\end{cases}
$$
and let $x_3=\lambda^2-x_1-x_2$ and $y_3=\lambda(x_1-x_3)-y_1$  

## Multiplication of a point by an integer
Multiplication is represented by the repeated addition of a point:
$nP=P+P+{...}+P$ 

## Why $4A^3+27B^2\neq0$ ? 
$4A^3+27B^2\neq0$ represent the discriminant of E. If this discriminant is 0, it means there are repeated roots, which we don't want in our curve.

---
## References
1. [[Elliptic Curves notes]]