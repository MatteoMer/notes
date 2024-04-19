1809202318:09
tags: 
# Calculate the 2^k * m form of a number

Divide the number by $2^1, 2^2,..., 2^k$ until the result of the division is not an integer. 
Now take the result of the last division and the last exponent, and you found the right form
##### Example:
$n=53$ 
$\frac {52}{2^1}=26$,$\frac {52}{2^2}=13$,$\frac {52}{2^3}=7.5$ 
Since 7.5 is not an integer, the form $2^k * m$ is $52=2^2*13$ 

---
## References
1. [[2. Literature notes/Miller-Rabin Test|Miller-Rabin Test]]