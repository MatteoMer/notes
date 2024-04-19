0212202317:32
tags: 
# Arithmetization oriented hash function

An arithmetization oriented hash function is a type of hash function that is designed to be more efficient with programs/systems that are not optimized for binary operations but instead with tools such as MSM or FFT.
#### Example
It's very expensive to prove the execution of a more traditional hash function such as SHA-256 in a zk-SNARK with KZG. With a AO oriented hash function, it would be way cheaper!

They tend to use some common design pattern such as a [[substitution permutation network]] as part of their design.
### Some AO Hash functions
- [[3. Permanent notes/Poseidon hash function|Poseidon]]
- Rescue
- Griffin

---
## References
1. [[2. Literature notes/Poseidon Hash Function]]