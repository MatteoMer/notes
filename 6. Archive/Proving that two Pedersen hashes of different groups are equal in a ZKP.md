1902202420:19
tags: 
# Proving that two Pedersen hashes of different groups are equal in a ZKP

Taking $X_p$ and $X_q$ as the pedersen commitment of the witness $(x, r_p, r_q)$ in their respective fields $p$ and $q$. 
## Naive approach
The naive approach would be to open both commitments in the circuit (with the witnesses as private inputs) but foreign arithmetics in ZKP is super expensive so it would cost so much to prove it in a circuit! 

## Paper approach
The paper propose a new protocol, used alongside a range proof that makes sure the witness fits both group.

### Protocol
**Parameters**:
With $G_p, G_q, H_p, H_q$ some generators of respectively $\mathbb{G_p}$ and $\mathbb{G_q}$ 
$b_c$ the bit-length of the challenge
$b_x$ bit-length of the witness x
$b_f$ Parameter controlling the probability of aborts

**Prover**:
- Choose some values $k,t_p,t_q$ such as $k \in \{0, ..., 2^{b_x + b_c+b_f}-1\}$, $t_p \in \{0,...,p-1\}$, $t_q \in \{0,...,q-1\}$
- Compute $K_p=kG_p+t_pHp$ and $K_q=kG_q+t_qH_q$
- Send $K_p$ and $K_q$ to the verifier
**Verifier**
- Generate challenge $c$ and sends it to the prover (with $c \in \{0, ..., 2^{b_c}-1\}$)
**Prover**
- Compute $z=k + cx$ in $\mathbb{Z}$.
- Compute $s_p= t_p + cr_p\pmod p$ and $s_q= t_q + cr_q\pmod q$
- If $2^{bx+bc} ≤ z < 2^{bx+bc+bf}$, abort
- Send $z, s_p, s_q$ to verifier
**Verifier**
- Verifies that $zG_p + s_pH_p=K_p+ cX_p$  and $zG_q + s_qH_q=K_q+ cX_q$. 
- If $2^{bx+bc} ≤ z < 2^{bx+bc+bf}$, abort
- Verifies the range proof (such as bulletproof)



---
## References
1. [Beyond the circuit: How to Minimize Foreign Arithmetic in ZKP Circuits](https://eprint.iacr.org/2024/265.pdf) 