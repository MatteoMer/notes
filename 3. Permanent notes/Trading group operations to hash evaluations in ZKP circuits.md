2102202416:14
tags: 
# Trading group operations to hash evaluations in ZKP circuits

Group operations in circuits are super expensive, especially when using a non native field.
The authors are giving as a solution to this problem, to precompute the solution outside of the proof, and then using an hash evaluation, the verifier can be sure that the prover is saying the truth. (that he knows a value that verifies the SM).
It aims to do some scalar multiplications without the need of [[3. Permanent notes/Elliptic Curves|EC]] operations (in circuit)
## Parameters
($\vec{x}, \vec{X}, x_h$): inputs of the prover, $\vec{x}$ is the secret value to be multiplied with, $\vec{X}$ the result and $x_h$ the hash of $\vec{x}$
$M$ is the relation to be proven s.t $\vec{X}=M\vec{x}$. It's asked for the relation to be hard to find.
$x_h=\sf{H}$$(\vec{x})$. where $\sf{H}$ is a collision resistant hash function (such as [[3. Permanent notes/Poseidon hash function|poseidon]])
## Protocol
**Prover**
Generate $\vec{k} \in \mathbb{Z_p^m}$, compute $\vec{K}=M\vec{k}$ and $k_h=\sf{H}$$(\vec{k})$
Send $\vec{K}, k_h$ to the verifier
**Verifier**
Generate challenge $c$, send it to prover
**Prover**
Compute $\vec{z}=\vec{k} +c\vec{x}$
Send $z$ to verifier alongside a proof that the computation of the hashes are valid.
**Verifier**
Verifies that $M\vec{z}=\vec{K}+c\vec{X}$ and that the proof is valid
## Questions
- How is it more efficient than precomputing the values in the circuit? (or as public inputs)
- Would like benchmarks against non naive implementations

---
## References
1. [Beyond the circuit: How to Minimize Foreign Arithmetic in ZKP Circuits](https://eprint.iacr.org/2024/265.pdf)