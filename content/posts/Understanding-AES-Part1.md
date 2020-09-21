---
title: "Understanding AES Part1"
date: 2020-07-23T03:05:43+05:30
draft: false
---

Hello Peeps,

AES is an algorithm widely used for different applications. It is an encryption algorithm and not used for creating hashes that means you can decrypt a data using the algorithm which is not possible in case of hashes. 🙂

AES is a symmetric key algorithm which means that it uses only one key for both encryption and decryption of the data. We will deep dive into each and every part of the mechanism to understand its working. Also, we will learn how my previous posts on Maths are related to it. 🙂 And we might also do some actual Mathematics now 😉

So, let’s get started.

In my previous posts, we had learnt the basic definitions of Groups, Rings and Fields. Here, first I will show you the relation amongst them. The following diagrammatic view along with the previous definitions given in my previous post, will give you a visualization.

We will mostly focus on Galois Field, being the base for AES Algorithm. Also, in cryptography, we almost deal with finite sets. So, now we will go more deeply.

A Finite Field or a Galois Field exists if they have p(m) elements where p is prime and m is a positive integer.

For example, there is a Finite Field which exists with 7 elements i.e. GF(7) -> here 7 is prime and 1 is a positive integer.

Again there is a Finite Field which exists with 27 elements i.e. GF(27) = GF(33) where 3 is prime and the power, 3 is a positive integer.

The Finite Field that we will be focusing on right now is the one with 256 elements written as GF(256) = GF(28), where 2 is the smallest prime number with 8 being the positive integer. And this is used in AES. This field is used in your web browser including wherever there is a usage of AES Algorithm.

Now there are two types of Finite Fields widely used in cryptography:

    Prime Fields where GF(p), m = 1
    Extension Fields where GF(pm), and m > 1

And we are interested in Extension Field with the smallest prime number, written as GF(2m).

Next, we are going to see how is a computation performed in Finite Fields. I will start with Prime Fields as the power is 1, so it will be easier for you to understand at first. Later we will look into the computation of the Extension Fields as well 🙂 You might get a clear picture of my definitions through these computations, I hope 🙂

So, here we go….

A Prime Field GF(p) is a field whose elements are integers {0,1,2,….,p-1}, where p is prime. Pretty Staightforward!!! 😉

Let a,b ∈ GF(p) with elements are {0,1,2,….,p-1}, then

    a + b ≡ c mod p
    a – b ≡ d mod p
    a * b ≡ e mod p
    a * (-a) ≡ 1 mod p

So, here some question arise, is it solving every condition of a Finite Field as has been discussed before??? Are the elements closed over the operators defined?? Do they have an inverse? Do they have an identity element? Do they belong to the set?? Just have some patience and look at the “mod” that has been used to satisfy our conditions for the elements belonging to a Finite set. Even if there is a problem in understanding, feel free to mention that and I will jot it down in complete details. 🙂

Finding inverse is a very important step in cryptography. We find the inverse using Extended Euclidean algorithm. In the above Field, we do need to find inverse of the elements but I will be explaining it later in my post. So, no worries 😛

Too much maths for now, I will be explaining about Extension Field which is used in AES in my next blog post. Till then, Happy Decoding. 🙂
