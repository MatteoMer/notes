1709202317:58
tags: #archive 
# Miller-Rabin Test

### Definition
The Miller-Rabin test is an probabilistic primality test: it's an algorithm that checks for a specific property known to prime numbers, and checks if this holds for the number checked.

I think it's related to Little Fermat's Theorem but I would need to double check.

### Algorithm
With $n$ the number to test:
	**Step 1**: Find $n-1=2^k*m$ 
	**Step 2**: Choose $a$ such that $1<a<n-1$ 
	**Step 3**: Compute $b_0=a^m \bmod n$ 
		_If_: $b_0=1$, n is not prime ou $b_0=-1$ n is probably prime _Else_:
	**Step 4**: Compute $b_1=b_0^2\bmod n,...,b_i=b_{i-1}\pmod n$ until $b_i\equiv\pm1\pmod n$ 
#### Warning
You have to test against both $1\bmod n$ and $-1\bmod n$ 
### Example
Is $n=53$ a prime number?

**Step 1**: $52=2^2*13$ 
**Step 2**: $a=19; 1<a<52$ 
**Step 3**: $b_0\equiv 19^{13} \equiv 30 \pmod {53}$; $30 \neq \pm1$ so we need to continue
**Step 4**: $b_1 \equiv 30^2 \equiv 52 \pmod {53}$ Since $-1 \equiv 52 \pmod {53}$ then $n$ is prime.

### How to calculate step 1 easily
Divide the number by $2^1, 2^2,..., 2^k$ until the result of the division is not an integer. 
Now take the result of the last division and the last exponent, and you found the right form
##### Example:
$n=53$ 
$\frac {52}{2^1}=26$,$\frac {52}{2^2}=13$,$\frac {52}{2^3}=7.5$ 
Since 7.5 is not an integer, the form $2^k * m$ is $52=2^2*13$ 


---
## References
1. [[6. Archive/Miller-Rabin Test|Miller-Rabin Test]]
2. [[Find the 2^k * m form of a number]]