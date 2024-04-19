1809202317:59
tags: 
# Miller-Rabin Test - Example

## Meta
This is an example of the [[3. Permanent notes/Miller-Rabin Test|Miller-Rabin Test]].
You can use [[Calculate the 2^k * m form of a number]] for step 1.
## Example:
Is $n=53$ a prime number?

**Step 1**: $52=2^2*13$ 
**Step 2**: $a=19; 1<a<52$ 
**Step 3**: $b_0\equiv 19^{13} \equiv 30 \pmod {53}$; $30 \neq \pm1$ so we need to continue
**Step 4**: $b_1 \equiv 30^2 \equiv 52 \pmod {53}$ Since $-1 \equiv 52 \pmod {53}$ then $n$ is prime.

---
## References
1. [[2. Literature notes/Miller-Rabin Test|Miller-Rabin Test]]