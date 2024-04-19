0101202412:15
tags: 
# Binius 

SNARKs and STARKs got big problems for computing traditional hash function because it uses bitwise operations, and in a finite field, it's very expensive to compute bitwise operation (while a normal computer it's cheap).

A proposed solution for this problem is to use binary fields and brakedown commitment scheme, which gives a more natural way to compute bitwise operations and it's also more hardware friendly.
## Binary Fields
Binary fields are fields of characteristic 2. They are in the form $\mathbb{F}_{2^n}$ for some $n$. 
The simplest binary field is $\mathbb{F}_2$ which is $\{0,1\}$.
Addition corresponds to the bitwise OR and multiplication AND.


---
## References
1. https://blog.lambdaclass.com/snarks-on-binary-fields-binius/