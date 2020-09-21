---
title: "Introduction to Finite Groups"
date: 2020-07-23T03:07:19+05:30
draft: false
---

Hello Folks,

This is my first post on a topic which is of my area of interest, “CRYPTOGRAPHY”. Being from a mathematics background, it always helped me in understanding the basic concepts used behind the widely used algorithms.

So, here I will be sharing some knowledge about cryptography basics and the actual mathematics behind it.

Don’t worry, I will not go harsh on you 😉

The goal of my post is to give a basic insight of Finite Group upon which the entire cryptography is based. So, I will be starting with the Set Theory, hoping that you guys might have some idea of it after learning it in your engineering or any equivalent course. Readers who desire an in-depth knowledge of cryptography and mathematics may find this post a bit useful or a reference guide in future ;).

So, let’s begin…

By the way, I will be defining everything symbolically as well, so let us first know what those mathematical symbols imply:

    ∀ means for all
    ∈ means belongs to
    ⊂ means subset of
    ∃ means there exists
    : means such that

By definition, Set means a collection of things. Each and everything which is collected in a Set is called an Element of the Set.

Suppose, S is a set of Natural Numbers, say N, then we can symbolically define it as:

S = {p : p ∈ N & p < n} ∀ n ∈ N

There are certain sets which belong to a larger set, they are known as subsets. For example, a set of Natural Numbers, N is a subset of a set of Real Numbers, R.

Symbolically written as, N ⊂ R.

We will continue getting into depth but first, let us go to the main part as well.

Mathematically, a group (G,*) consists of a set G and a binary operator *, such that it satisfies the following rules:

    * is closed on G, i.e. if a,b ∈ G, then a*b ∈ G
    * is associative i.e. if a,b,c ∈ G, then a*(b*c) = (a*b)*c
    G contains an identity element i.e. ∃ e ∈ G : ∀ a ∈ G, a*e=a
    G contains an inverse element i.e. ∀ a ∈ G, ∃ a-1 ∈ G : a * a-1 = e

A bit complex?? 🙁

No worries!!

In normal language, a Group is a set of arbitrary elements on which an abstract operation is performed satisfying certain rules, as written above.

We will be only focusing on Finite Groups having a finite group order, which is the cardinality of the Group.

Suppose, we have a set A, of natural numbers consisting of n elements as represented below:

A = {0,1,2,3,…,n}

The above mentioned set is finite as we can see there is a fixed number of elements. Now, if the entire set abides by the rules of a Group, mentioned above, they can be called as a Finite Group. And if it is a Finite Group, it has to be an order.

So, let there be an element a ∈ G, if ∃ a smallest positive integer m, such that aᵐ = e, where e is the identity element of the group, then m is called the order of the Group G.

The order of a group G is denoted by ord(G) or |G| and the order of an element a by ord(a) or |a|.

Now, your next question may arise, why Finite Groups??? 😕

Algorithms such as AES are based on Galois Field, also known as Finite Field. This is again based on Finite Groups. I will be talking about it in my upcoming blog post. So, no worries 😛

Basically, we use Finite Fields because it allows mathematical operations to scramble data easily and effectively. Galois Field consists of numbers which are a combination of 0 and 1 where we define a finite range and perform our operations within that finite range. The range specified always remains constant no matter how many operations are performed.

That’s it for now, feel free to ask questions. I will be continuing this blog and you never know, we might come up with something more interesting. Till then, Happy Decoding!!! 🙂