0412202320:25
tags: #archive
# Garbled Circuits Primer - Vitalik

Garbled Circuits are the simplest form of general purpose MPC.

Two parties: Alice and Bob, wants to compute some function $f$ with two different input as parameters: `alice_input` and `bob_input`. 
Both parties wants to keep secret their input and doesn't want the other party or any other observer to learn anything about their input.
Ideally they would both learn anything except the result of the function $f$. 

The idea of garbled circuits solves this:
- Alice performs a procedure called **garbling**. Garbling means transforming a normal circuit into his encrypted version, meaning all gates and inputs are encrypted. She passes the encrypted circuit and input to Bob.
- Bob use a technic called **1-of-2 oblivious transfer** to learn the equivalent encrypted form of his inputs, without letting Alice know which inputs he obtained.
- Bob run the encrypted circuit on the data, gets the answer and passes it along to Alice.
## Setup the scheme
For every gate of our circuit (that have either 0 or 1 as output), we create two labels (256bits-numbers): one that represents 0 and another that represents 1.
We do this for every intermediate wires but not the outputs ones. 
## Garbling gates
A map of each combination of inputs and output is encrypted in a way that you can decrypt only if you have the right input wires. This is the garbling.
## 1-of-2 oblivious transfer
In this step Alice sends to Bob the right labels corresponding to his outputs without revealing what his input is.
## Evaluation
Bob then evaluates the gates with all the labels he learned about. Since you can decrypt the output gates only if you have the right inputs, he discover the answer to the circuit gate by gate.


---
## References
1. https://vitalik.eth.limo/general/2020/03/21/garbled.html