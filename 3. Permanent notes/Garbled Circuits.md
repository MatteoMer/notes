0412202321:15
tags: 
# Garbled Circuits

Garbled Circuits are the simplest form of general purpose MPC.

Two parties: Alice and Bob, wants to compute some function $f$ with two different input as parameters: `alice_input` and `bob_input`. 

Both parties wants to keep secret their input and doesn't want the other party or any other observer to learn anything about their input.

Ideally they would both learn anything except the result of the function $f$. 

The steps of a garbled circuit scheme is:
1. [[Setup a garbled circuit scheme|Setup the scheme]]
2. [[Garbling Gates]]
3. [[1-of-2 oblivious transfer]]
4. [[Evaluation of a garbled circuit|Evaluation]]

---
## References
1. [[Garbled Circuits Primer - Vitalik]]