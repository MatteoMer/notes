1809202315:28
tags: 
# Miller-Rabin Test

The Miller-Rabin test is a test that checks if a number if prime or not using probabilities: it's an algorithm that checks for a specific property known to prime numbers, and checks if this holds for the number checked.

The Miller-Rabin test exploits the [[3. Permanent notes/Little Fermat's Theorem|Little Fermat's Theorem]] to detect the primality of a number.
## Usage
It's widely used in cryptography, where finding prime numbers is key.
## Algorithm
With $n$ the number to test:
**Step 1**: Find $n-1=2^k*m$ 
	**Step 2**: Choose $a$ such that $1<a<n-1$ 
	**Step 3**: Compute $b_0=a^m \bmod n$ 
		_If_: $b_0=1$, n is not prime ou $b_0=-1$ n is probably prime _Else_:
	**Step 4**: Compute $b_1=b_0^2\bmod n,...,b_i=b_{i-1}\pmod n$ until $b_i\equiv\pm1\pmod n$ 
#### Warning
You have to test against both $1\bmod n$ and $-1\bmod n$ 
## Note
To calculate $n-1=2^k*m$ you can use [[Calculate the 2^k * m form of a number]] 

## Examples
[[Miller-Rabin Test - Example]]

---
## References
1. [[2. Literature notes/Miller-Rabin Test|Miller-Rabin Test]]