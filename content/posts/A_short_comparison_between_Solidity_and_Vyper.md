---
title: "A Short Comparison Between Solidity and Vyper"
date: 2020-11-15T00:45:45+05:30
draft: false
---


<p>
Smart contracts are made with the concept of bringing more applications of blockchain and not just sticking to being used for cryptocurrencies. They are just simple pieces of code adding logic to a problem to find the solution. Solidity is the very first programming language that is created for writing smart contracts for the Ethereum blockchain platform. And so is Vyper but vyper is not the first programming language but has been built recently.
</p>

<p>
But why a new language?
</p>
</p>
Vyper has been built to be simpler as compared to solidity. So it doesn't have many of the functionalities related to the Object-Oriented Programming(like inheritance, overloading). It intentionally doesn’t aim to be a Turing complete language.
</p>
<p>
Turing-complete language means a language that can solve all kinds of mathematical computations.
So more functionalities are equal to more complexities and more complexities may lead to security risks, as we have observed in solidity. And so we have vyper with some modifications taking in mind the complexities and loopholes, that solidity has. 
</p>
<p>
A smart contract code written in solidity or vyper gets compiled first into bytecodes. Bytecodes are nothing but machine code representation of the program. These bytecodes then get executed in the Ethereum Virtual Machine or EVM, which is just a Stack-based virtual running environment. We will talk about EVM in more detail in a different post separately.
Every node in the ethereum network runs EVM. 
</p>
<p>
Let's get back to the various changes that have been made in vyper while taking care of the flaws in solidity, in brief : 
</p>
<p>
1. Apart from the change related to the Object-Oriented Programming, Vyper also takes care of the infinite length and recursive loops to keep a check on the problem of exceeding the gas limit while executing a function. 
</p>
<p>
2. Integer over/underflow vulnerability is already taken care of in the Vyper while in solidity, the safe-math library has to be implemented to avoid this vulnerability. 
</p>
<p>
3. There are only two methods to call a function in vyper and these functions do make exceptions in case of invalid transaction unlike a call, send, delegate call functions used in solidity. 
</p>
<p>
4. Modifiers are also no longer used in Vyper as it has been observed that they would mislead the code in solidity by including a check once, before execution, then another check after the execution and this sometimes would result in some changes and can be quite confusing.  
</p>
<p>
5. Usage of Inline assembly has been removed as well in Vyper so that no low-level code could be embedded within the program. This may lead to some security issues too.
</p>
<p>
6. Vyper has partially addressed the reentrancy vulnerability. In case the state of the contract is not changed before calling an external contract, vyper may fall prey to reentrancy. We can never forget the famous DAO attack that happened in ethereum based smart contracts, due to the vulnerability in solidity.
</p>
<p>
7. Vyper makes use of __init__ for declaring constructors. Solidity initially would use the name of the contract but now it has been changed in solidity as well. The famous Rubixi attack is an example.
</p>
<p>
Finally, we can conclude that Vyper is, of course, a good alternative to solidity, but not a replacement for it. Many modifications have to be made yet, as not every loophole is taken care of.  Also, some of the features had to be removed but vyper is not meant to be a language for every use case. 
</p>


References:

<p> <a href="https://youtu.be/rqfM6cxXHB8"> Understanding Vyper: The slick New Ethereum language </p>
<p> <a href="https://www.researchgate.net/publication/339997773_Vyper_A_Security_Comparison_with_Solidity_Based_on_Common_Vulnerabilities#:~:text=Vyper%20has%20been%20proposed%20as,Solidity%20since%20the%20system's%20inception."> Vyper: A Security Comparison with Solidity Based on Common Vulnerabilities </p>
<p> <a href="https://vyper.readthedocs.io/en/stable/"> https://vyper.readthedocs.io/en/stable/ </p>
<p> <a href="https://blockgeeks.com/guides/understanding-vyper/"> UNderstanding Vyper </p>
<p> <a href="https://hashgard.medium.com/deep-analysis-of-vm-what-virtual-machines-are-used-by-ethereum-and-eos-af925b9408a3"> Deep Analysis of EVM </p>
<p> <a href="https://blockgeeks.com/guides/understanding-vyper/"> Understanding Vyper </p>





