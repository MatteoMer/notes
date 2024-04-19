2509202315:31
tags: 
# Diffie-Hellman key exchange protocol

The DHP is a protocol that is used to create a shared secret (a key) with the property that even in an environnement where everything is public and watched, it's possible the users to exchange keys secretly.

It's using the [[Discrete Logarithm Problem]].
## Protocol
- Both users Alice and Bob agree on a large prime $p$ and a non-zero integer $g$. This information is available to the public.
- Alice picks a secret integer $a$ and Bob does the same by picking $b$. They keep it as a secret.
- Alice computes: $A\equiv g^a\pmod p$  and Bob: $B\equiv g^b\pmod p$.
- It's not possible to compute $a,b$ by looking at $A,B$ (DLP).
- They both share $A$ and $B$ to the insecure channel they're talking by.
- Alice then computes: $A'=B^a$ and Bob $B'=A^b$.
- Both values are actually the same $$A'=B^a=(g^b)^a=g^{ba}=(g^a)^b=A^b=B'$$ and it's not possible to compute it without $a$ or $b$.

---
## References
1. [[An introduction to Mathematical Cryptography Chapter 2]]