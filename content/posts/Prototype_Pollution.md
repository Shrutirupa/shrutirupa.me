---
title: "Prototype Pollution - Part1"
date: 2022-02-03T03:39:39-05:00
draft: false
---

With time, attackers are finding new ways to exploit an application. We may have been using the application for a long time and are still unaware that it may be vulnerable to recent exploits. We learned about different security flaws and ways to detect them in my previous blog posts. You check them out <a href="https://shrutirupa.me/posts/"> here</a>. Today, we will be learning about an attack that is not quite common, but it is not that uncommon too - <b> Prototype Pollution</b>. We will try to understand the vulnerability in layman's language to explore the technical aspects of the same with more ease later. </br>

This attack is more specific to the OOPs(Object Oriented Programming System) concept used in Javascript, so we will begin with comprehending the basics of javascript that we need to know for examining this attack. </br>

Let us get started. :) </br>

The prototype is a massive thing in javascript. Before moving forward with the understanding of the vulnerability, let us comprehend what a prototype in general means. </br>

A prototype is an initial version of a product from which other forms of the product get developed. So, taking the exact definition from here, a prototype in javascript  is considered a similar type of specific object defined previously. This is done based on the object's structure and properties. So, if you modify the prototype in one place, it will affect the other objects' properties in the entire application. </br>

By definition, in JavaScript, an object is a standalone entity with properties and type. It is a collection of pairs that contain keys and their corresponding values. </br>

Basically, in Object-Oriented Programming, we see an object inheriting some similar properties from its parent. The attackers take advantage of this to exploit an application, i.e. if an external user can perform some modification at this level, this becomes a matter of significant concern. This is where prototype pollution comes into the picture. </br>


Let us understand this in more detail. </br>

Going through the below example: </br> 

<img src="/images/proto/proto1.PNG" />

We see var1 and var2 have a lot in common except for one comment added in object var2. So, instead of rewriting or duplicating the entire properties of an object again, we can take advantage of the prototype that we learned just now. So here, var2 is a prototype of var1, i.e., it is inheriting properties of var1 along with having some properties of its own. So we can rewrite the code using the "__proto__" keyword in the following manner. This way, we can override the existing property as well. </br>

<img src="/images/proto/proto2.PNG" />

Of course, this is not the right way to write your javascript code, and this functionality is deprecated but to understand what prototype pollution at a more superficial level is, this level of understanding is enough. </br>

Suppose an attacker gets a scope to enter their input for polluting. In that case, they can add a new kind of variable(that does not even exist) whose prototype is given to an already existing variable. As mentioned before, the attacker can also override an existing property. </br>
So to examine a simple attack scenario in the real world, an attacker would manipulate the keyword “__proto__” to change the application's behavior using Global Objects. They can create a new property or override an existing property, affecting the properties of the existing objects, hence polluting the prototype. <br>

A global object is an object that always exists in the global scope. It holds variables that are available everywhere. <br>

Once you know that the application is vulnerable to prototype pollution, the mitigation steps will not be very complex. Mitigating prototype pollution does not require many complicated steps. Following good programming practices and proper sanitization of the input field can help a lot. Of course, nothing is 100% secure, but we can always reduce the risk of any vulnerability through proper and regular audit checks and maintaining all the required security measures. </br>
We will explore this attack in more detail with some examples in my upcoming blogs. So, Stay Tuned!!! </br>

