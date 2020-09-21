---
title: "Introduction to Fields"
date: 2020-07-23T03:05:06+05:30
draft: false
---

Hello Folks,

I hope my last post was useful to you all and you could understand at least the definition that I had mentioned.

Basically, it is not that easy to understand group theory at once, but I can assure you that once you are able to understand their application in Cryptography, you might start understanding it and hence, loving it as well. This had happened to me though 😛

So, let us start with the mathematical definition of Fields and then we will head towards my idea on my next blog. 🙂

In my last blog, we learned about the definition of Rings, now let us learn what Field is.

A Field is a set, say F with two binary operators, + and  * such that the following conditions are satisfied:

     + is closed on F, i.e. ∀ a,b ∈ F, a + b ∈ F
     * is closed on F i.e. ∀ a,b ∈ F, a * b ∈ F
     + is associative i.e. if a,b,c ∈ F, then a+(b+c) = (a+b)+c
     F contains an identity element on +  i.e. ∃ 0 ∈ F : ∀ a ∈ F, a+0=a
     F contains an inverse element on + i.e. ∀ a ∈ F, ∃ –a ∈ F : a + (-a) = 0
     ∀ a,b ∈ F, a + b = b + a
     ∀ a,b ∈ F, a * b = b * a
    ∀ a,b,c ∈ F, a * ( b * c ) = ( a * b ) * c
    ∀ a,b,c ∈ F, (a + b) *c  = a * c + b * c
     F contains an identity element on *  i.e. ∃ 1 ∈ F and 1 ≠ 0 : ∀ a ∈ F, a*1=a
     F contains an inverse element on *  i.e. ∃ -a ∈ F and -a ≠ 0 a : ∀ a ∈ F, a*(-a) = 1

So, a Field is just a Commutative Ring whose every non-zero element has a multiplicative inverse.

I am just going with the basic definitions for now, we will get into details eventually. 😛

Now, we have finally headed towards the topic which is  of utmost importance for my next blog posts. The topic is “Finite Fields”.

Finite Field is also known as Galois Field, which is the base for AES Algorithm. As the term suggests, a Field consisting of finite number of elements is a Finite Field. But there is a catch!! :O

In my previous post about Finite Groups, we had learnt about order of a Group. Even in the case of Fields, we have an order defining it’s Cardinality.

Hence, the order of a Finite Field is either a prime or a power of prime.

This is what we will be focusing on from my next posts. We will learn about AES and let us see if we can come up with something similar of our own. 😛

These definitions will be more clear in my upcoming posts. Till then, happy decoding 🙂

PS: I will be writing more blog posts on Group Theory and will penetrate deep into it. 🙂
