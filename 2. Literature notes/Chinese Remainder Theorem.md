1809202316:57
tags: #archive 
# Chinese Remainder Theorem

### Introduction
The Chinese Remainder Theorem wants to solve a system of congruence. 
A congruence is when two numbers are the same in mod n. For example, $a \equiv b \pmod n$ is a congruence.
This theorem is widely used in cryptography, as it allows to compute large integers by replacing one costly computation by multiple ones with smaller integers (so less costly).
For example Fast Fourier Transform is using it.

#### Simplest system of congruence
The simplest system of congruence is (with $gcd(m,n)=1$)
$$\begin{aligned}
x \equiv a \pmod n\space and\space x\equiv b\pmod m

\end{aligned}$$
### Theorem
Let $m_1, m_2, ..., m_k$ to be integers that are relatively prime to each other.
Let $a_1, a_2, ..., a_k$ to be arbitrary integers.
Then the solution of simultaneous congruence has a solution $x$ such that $x=c$. 
Further, if $x=c\space and\space x=c'$ then $c \equiv c' \pmod {m_1\cdot m_2\cdot\space ...\space \cdot m_k}$  

### Example 
Let $x\equiv2\pmod3,x\equiv3\pmod7,x\equiv4\pmod{16}$  
Chinese Remainder Theorem says there an unique solution $\bmod 336$ since $336=3\cdot7\cdot16$

- We start with $x=2$ as a solution to solve $x\equiv2\pmod3$. We can now say that $x=3y+2$.
- We will use this value of x to replace it in $x\equiv3\pmod7$. We know have $2+3y=3\pmod7$ 
- We can also write it as $3y\equiv1\pmod7$ 
- $5$ is the multiplicative inverse of 3 $\bmod 7$. We will use it to divide the by each side.
- $3\cdot5\cdot y\equiv1\cdot5\pmod7$ so $y\equiv5\pmod7$. We can now $y$ in $x=3y+2$ that we talked about just before.
- $x=3\cdot5+2=15+2=17$. We've now solve the first congruence. We can use this result to solve the other one. Remember this solution is $\bmod21$.
- We can now say that the first congruence can be written as $x\equiv21z+17$. With that you can calculate the second one just like before.
---
## References
1. [[6. Archive/Chinese Remainder Theorem|Chinese Remainder Theorem]]
2. [[Chinese Remainder Therorem usage]]