1809202318:25
tags: 
# Chinese Remainder Theorem - Example

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
1. [[2. Literature notes/Chinese Remainder Theorem|Chinese Remainder Theorem]]