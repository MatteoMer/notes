2209202322:15
tags: 
# Speeding up EC computation

Computations in [[Elliptic Curves|EC]] groups are more complex than in normal groups. For example you can easily see that [[Elliptic Curve Addition]] is way more complex that normal addition.

But we can optimize this computation, for example by using the [[Projective space]] instead of the [[Affine Space]]. 
## Note
The fact that computation in EC is more complex can be pretty good in some cases, because it's also more difficult for attackers to compute as well!

For example some algorithm that are aiming to solve the DLP in subexponential time are not working in EC computations.

Because of that we can take way smaller fields to do ECC. 


---
## References
1. [[EC SW Projective Representation]]