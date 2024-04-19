1909202322:16
tags: 
# Elliptic Curve Addition
In an elliptic when we want to add two points $P$ and $Q$ to get a third point we need to find the line $L$ that crosses $P$ and $Q$ and find the intersection $R$ of this line on $E$.

Then with $R=(a,b)$ the sum of $P$ and $Q$ is defined to be the reflection $R'=(a,-b)$.
![[Pasted image 20230919184229.png]]
We also need to acknowledge that $\mathcal{O}$ is the [[Point at Infinity]] and lies on every line.
## Remarks on point addition
- If we want to do $P+P$, we take $L$ as the tangent of $E$ at $P$.
- If we want to do $P+P'$, we will not find any intersection on the curve. That's where the [[Point at Infinity]] comes useful. We can then say that $P+P'=\mathcal{O}$. 

## Note
- The algorithm to compute a point addition can be found [[Elliptic Curve Addition Algorithm|here]]
- We can also do [[EC Addition over Finite Fields]]

---
## References
1. [[2. Literature notes/Elliptic Curves]]