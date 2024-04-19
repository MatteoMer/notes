2709202313:57
tags: #archive 
# Polynomials

A polynomial is an expression that consists of variables and coefficients that involves: additions, substraction and multiplication. 

An univariate polynomial is in the form $p(x)=a_0+a_1x^1+a_2x^2+...+a_nx^n$.
We can also write it in the form $\sum\limits_{{j=0}}^{{m}}a_jx^j$.
Here $a$ is the coefficient and $x$ the variable.
$n$ is called the degree of the polynomial.

If $R$ is the type of coefficient ($a\in R$ ). 
Then the set of all univariate polynomials with coefficients in $R$ is written $R[x]$.

Usually we call an univariate polynomial a _polynomial_ and we write $P(x)\in R[x]$.
The constant term $a_0$ can also be written $P(0)$.

If all coefficients are zero then the polynomial is called the *zero polynomial*.
If the constant is one and all the other coefficients are zero, it's called the *one polynomial*.

We call the coefficient with the highest degree the *leading coefficient*, written as $Lc(P)=a_m$.

We can restrict $R[x]$ to a maximum degree that cannot be exceeded. For example $R_\leq{m}[x]$ means that all the degree must $\leq m$. 

The degree of the zero polynomial is $-\infty$. 
## Polynomials over a field
Polynomials over a field $\mathbb{F}$ is written in the same form as a classical one but $\forall a_i \in p(x): a_i\in\mathbb{F}$.  
## Polynomial arithmetic
Polynomial arithmetic is pretty similar to integers.
With $a(x)=\sum\limits_{{j=0}}^{{m_1}}a_jx^j$ and $b(x)=\sum\limits_{{j=0}}^{{m_2}}b_jx^j$
$$a(x)+b(x)=\sum\limits_{{j=0}}^{{max(m_1,m_2)}}(a_j+b_j)x^j$$
$$a(x)\cdot b(x)=\sum\limits_{{j=0}}^{{m_1+m_2}}\sum\limits_{{i=0}}^{{j}}a_i\cdot b_{j -i}{x^j}$$
$$a(x)-b(x) = a(x)+(b(x)*-1)$$
## Evaluation of a polynomial
We can evaluate a polynomial $p(x)$ at a point $b$ by doing $p(b)$, which means doing $$\sum\limits_{{j=0}}^{{m}}a_jb^j$$
## Euclidean division in polynomials 
Euclidean division is defined for polynomials.
It means that when there's $A,B\neq 0\in R[x]$ with $Lc(B)^-1\in R$, there exists two polynomials $Q,P\in R[x] \text{ s.t } A=Q\cdot B+P$. and $deg(P) < deg(B)$.

### Notation
We use the following notation:
$A \text{ div } B=Q$, $A\bmod B=P$.
If $A\bmod B=0$ we say that $A$ is divisible by $B$ and we note it $B|A$. 
$B$ is a factor of $A$.

## Polynomial Euclidean Algorithm
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
## Prime factors in polynomials
The analog to prime numbers in polynomials is *irreducible polynomials*, which is defined as a polynomial that cannot be factored into the product of two others non-constant polynomials using euclidean division.

Irreducible polynomials are what prime numbers are to integers, building block from which every polynomial are constructed.
Let $P\in R[x]$ there's always some irreducible polynomials $F_1, F_2, ..., F_n\in R[x]$ s.t:$$F_1\cdot F_2\cdot...\cdot F_n=P$$
It's called the prime factorization of $P$.
## Root of a polynomial
Points where a polynomial evaluates to 0 are called roots of the polynomial.
Let $P\in R[x], P(x_0)=0$ then $x_0$ is a roof of $P$.
The set of roots of $P$ is denoted as $P_0(P)=\{x_0\in R| P(x_0) = 0\}$.

Roots are interesting especially looking at the prime factorization, since we can show that for any root $x_0$ of $P$, the polynomial $f(x)=(x-x_0)$ is a prime factor of $P$.

Finding the roots of a polynomial is sometimes called *solving a polynomial*. It's consider a difficult problem to solve.

If a polynomial $P$ has $deg(P)=m$. It has a most $m$ roots, but can have less.
## Lagrange Interpolation
One useful property of a polynomial of $deg(m)$ is that the polynomial is completely defined on $m+1$ points.
It means we can derive a polynomial from a set $S$ of points. $$S=\{(x_0,y_0),...,(x_n,y_n)|x_i\neq x_j\forall i,j \}$$
It means that polynomials have the property of being defined by a list of point $S: (x,P(x))\forall x\in R$
It's probably useful to represent a polynomial like this (maybe we can use ECC calculation with the points or represent an ECC as a polynomial).

We will use Lagrange Interpolation to find the polynomial from the set of points $S$. 

### Definition
Given a set $S$ of points, a polynomial $P$ of degree $m$ with $P(x_i)=y_i$ $\forall$ pairs $(x_i,y_i)\in S$ is given by the algorithm:
![[Pasted image 20230927174727.png]]

We usually it to find an $y$ for a specific $x$. 

---
## References
1. [[6. Archive/Polynomials]]