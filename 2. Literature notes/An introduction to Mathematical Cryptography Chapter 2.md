2409202313:43
tags: #archive 
# An introduction to Mathematical Cryptography Chapter 2

## Primitive root theorem
The primitive root theorem tells us that there's a $g$ whose powers gives any element of $\mathbb{F}_p^*$.
These elements element ($g$ for example) have an order of $p-1$.

$g$ is called a **primitive root**, this is the number whose powers generate a group $G$ where the elements are all the elements of $\mathbb{F}_p^*$ in some order.
$$\mathbb{F}_p^*=*\{1,g,g^1,g^2,g^3,...,g^{p-2}\}\pmod p$$
Note that $g^{p-1}=1$ by Little Fernat's Theorem.
### Note
If we want to find the generator of a subgroup of order $n$, we need to find for elements in the field that have an order of $n-1$. 
## Discrete Logarithm Problem
The discrete logarithm problem (DLP) exists in different versions for example using $\mathbb{F_p}$ or elliptic curves

### Definition
Let $g$ a primitive root of $\mathbb{F}_p$ and $h$ a non-zero element of $\mathbb{F}_p$. 
The Discrete Logarithm Problem is to find$$g^x\equiv h\pmod p$$
$x$ is called the discrete logarithm of $h$ to the base $g$ and is denoted by $log_g(h)$.

### Note
- If there's one solution to the congruence, there's infinitely more. 
	If $x$ is a solution then $x+k(p-1) \forall k$ are solutions.
	In other words, we can say that $log_g(h)$ is defined by adding or substract multiples of $(p-1)$. We can say that $log_g(h)$ is defined on $\bmod{p-1}$. 
	
	Sometimes we define DLP as the integer $x$ lying between $0$ and $p-2$ satisfying $g^x\equiv h\pmod p$.

## General Definition of the discrete logarithm problem
In the definition of the DLP, we say that $g$ must be a primitive root and the group law to be multiplication, but it doesnt have to be the case. We can generalize the DLP like this:
Let $G$ a group and $\cdot$ be the group law.
The DLP is, for $g,h\in G$, find $x$ s.t: $$\underbrace{ g \cdot g  \cdot g \cdot \text{ ... }\cdot g}_{x \text{ times}}=h$$
## Diffie-Hellman key exchange protocol 
The DHP is a protocol that is used to create a shared secret (a key) with the property that even in an environnement where everything is public and watched, it's possible the users to exchange keys secretly.

This is using the DLP for the exchange to be secure.

### Protocol
- Both users Alice and Bob agree on a large prime $p$ and a non-zero integer $g$. This information is available to the public.
- Alice picks a secret integer $a$ and Bob does the same by picking $b$. They keep it as a secret.
- Alice computes: $A\equiv g^a\pmod p$  and Bob: $B\equiv g^b\pmod p$.
- It's not possible to compute $a,b$ by looking at $A,B$ (DLP).
- They both share $A$ and $B$ to the insecure channel they're talking by.
- Alice then computes: $A'=B^a$ and Bob $B'=A^b$.
- Both values are actually the same $$A'=B^a=(g^b)^a=g^{ba}=(g^a)^b=A^b=B'$$ and it's not possible to compute it without $a$ or $b$.



---
## References
1. [[Chapter 2 an intro to math crypto]]