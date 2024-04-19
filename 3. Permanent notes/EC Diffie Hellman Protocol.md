2509202315:10
tags: 
# EC Diffie Hellman Protocol

This implementation of [[Diffie-Hellman key exchange protocol]] uses [[3. Permanent notes/Elliptic Curves|Elliptic Curves]] instead of $\mathbb{F_p}$.

## Protocol
- A trusted party chooses and publishes a (large) prime $p$ and an EC $E$ over $\mathbb{F_p}$ and a point $P\in E(\mathbb{F_p})$.
- Alice chooses a secret integer $n_A$ and computes $Q_A=n_AP$. (using [[Scalar Multiplication in EC]])
- Bob does the same with $n_B$. 
- Alice sends $Q_A$ to Bob that sends her $Q_B$.
- Alice computes the point $n_AQ_B$ and Bob $n_BQ_A$. 
- This is the shared secret value.

---
## References
1. [[6. Archive/EC Diffie Hellman Protocol]]