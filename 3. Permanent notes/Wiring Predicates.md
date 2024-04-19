0804202411:42
tags: 
# Wiring Predicates

 Wiring predicates are functions in an arithmetic circuit that encodes which pairs of gates at the layer $i+1$ is connected at a certain gate at layer $i$ (for example a gate $a$ could be connected to $b$ and $c$ for example). 
 
 It can be defined like this:
 $$in_{1,i},in_{2,i}: \{0,1\}^{k_i}\rightarrow\{0,1\}^{k_{i+1}}$$ For our example we would write: $in_{1,i}(a)=b$ and $in_{2,i}(a)=c$ 

---
## References
1. [[00.Proofs, Args, ZK Session 4]]