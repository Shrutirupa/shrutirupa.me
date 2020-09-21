---
title: "Introduction to Rings"
date: 2020-07-23T03:04:40+05:30
draft: false
---

Hey All,

This is the continuation of my previous post where I had discussed about Finite Groups.

It is relevant to everyone who is willing to know about how algorithms are made and what makes them work so well in our real life. So, here we will be learning about rings but before that, let us understand what are Abelian Groups.

A commutative group is called an Abelian Group. So, mathematically, we represent it as:

Suppose  (G,*) is  a Group, and there are two elements a,b ∈ G, if

a * b = b * a ∀ a,b ∈ G, the Group, G is an Abelian Group.

Next, we will head towards the definition of Ring.

You guys might be thinking, why are we discussing about Maths so much. We will get to know about it in my upcoming posts. 😉 So be patient and let’s get started 🙂

A ring is a set, say R with two binary operators, + and  * such that the following conditions are satisfied:

     + is closed on R, i.e. ∀ a,b ∈ R, a + b ∈ R
     + is associative i.e. if a,b,c ∈ R, then a+(b+c) = (a+b)+c
     R contains an identity element i.e. ∃ e ∈ R : ∀ a ∈ R, a+e=a
     R contains an inverse element i.e. ∀ a ∈ R, ∃ –a ∈ R : a + (-a) = e
     ∀ a,b ∈ R, a + b = b + a
     ∀ a,b ∈ R, a * b ∈ R
     ∀ a,b,c ∈ R, a * ( b * c ) = ( a * b ) * c
     ∀ a,b,c ∈ R, a * ( b + c ) = a * b + a * c

Here, + is the binary operator in R with respect to R being an Abelian group. * has to fulfill some extra conditions to make it a Ring i.e. {R,+,*}

So, the extra conditions that R should fulfill are:

1. R must be closed with respect to the operator * => Rule 6

2. R must be associative with respect to the operator * => Rule 7

3. * must be distributive with respect to the operator * => Rule 8

A ring {R, +, * } can be commutative, when

∀ a,b ∈ R, a * b = b * a

I hope, it’s not going too complex for you. 😉 Next, I will be discussing about Fields and then we will come to know what a Finite Field is.

Algorithms such as AES are based on Finite Fields. We will also get to know, how AES is based on Finite Field and how it works in details.

I hope that my posts are relevant to whoever is interested in this domain. Till then, happy decoding 🙂