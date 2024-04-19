1909202322:35
tags: 
# Elliptic Curve Addition Algorithm
To make an [[Elliptic Curve Addition|addition on an EC]] we can follow this algorithm:

With $E$ an [[Elliptic Curves|elliptic curve]] and let $P_1,P_2 \in E$ two points.
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

---
## References
1. [[2. Literature notes/Elliptic Curves|Elliptic Curves]]