---
title: "Magecart Attack"
date: 2021-06-01T20:13:57+05:30
draft: false
---

<p>
The news about a cyber attack in a big enterprise is not new. We keep on hearing about such attacks as to how millions of data are being stolen or leaked and can be found on the Dark Web. We are already aware of this scenario. As I always mention in my articles, nothing is 100% secure, so, as security professionals, it is important for us to take all the necessary precautions and be aware of the recent technologies and their respective attacks.  You can check out my previous blogs <a href="https://shrutirupa.me/posts/ "> here </a>, where I have covered a number of important security jargon that a security professional should be aware of.
</p>

<p>
Well, in this blog, we will be learning about an interesting topic which is Magecart.
So let's get started.
</p>
<p>
Magecart is basically, a group of hackers performing cyberattacks. Their main target is ecommerce websites. They make use of digital skimming to steal customer’s credit card information. 
The term “magecart” roughly came from the famous e-commerce website - Magento. 
</p>
<p>
Now let us start with understanding what does Skimming mean?
</p>

<p>
Skimming is a fraudulent practice performed by hackers or malicious users to steal credit card details from the users. These attackers would make use of physical devices such as skimmers, which are installed in the devices such as ATMs to steal the sensitive information.
This leads us to comprehending the meaning of Digital Skimming a bit. Thus, the malicious activity of stealing PII-Personally identifiable information (credit card or payment card) details during a digital transaction comes under the Digital Skimming.
</p>

<p>
Now the next question is what exactly happens in a digital skimming and how do the magecart attackers steal the PII details?
</p>

<p>
They mostly make use of the advertisement and tracking javascripts which are loaded from the third party. If the third party gets compromised, it compromises the product using them. The attackers use highly obfuscated malicious javascript code  where they mention the path to a different malicious URL. As a result, when the victim user is clicking on the payment option, and entering their details, this information not only goes to the payment gateway but also to the crafted url mentioned in the obfuscated javascript code. The attackers may use some other kinds of attacks like formjacking or supply-chain as well to perform the magecart attack. 
</p>

<p>
The domain that these attackers use, also seem to be legitimate because these are highly sophisticated hackers who use google cloud or AWS for the domain names. The domain names that they use look similar to the genuine names, i.e. most probably they mimic the known existing domains. They make use of the mechanism to detect the kind of browser the victim user uses. And in case, a user makes some investigation on their seem-to-be legitimate url, the attackers get aware of the activity.
</p>

<p>
Thus, the attack seems to be pretty serious. There have been plenty of cases where large organizations or enterprises have been the victims of such magecart attacks. Millions of users’ data got leaked and sold on the dark web. Some of the prominent companies which got affected by this attack are British Airways, NutriBullet, TicketMaster. 
</p>

<p>
It is always better to be careful and aware of these kinds of attacks. There is no perfect way to mitigate magecart attacks but we can definitely take precautionary measures to reduce the risk. 
There should be some detection tools that can be used to detect such malicious injections. Once detected, it should be blocked directly, at first, and later can be explored.
</p>

<p>
The basic good security practices should be implemented in the organization and each and every application should be patched up to date. A sandbox environment could be implemented along with some effective monitoring tools.
Another way to reduce risk of MageCart Attacks could be CSP which stands for Content Security Policy. This header is used to prevent attacks that involve injection of malicious content in the context of the web page. Some examples of such attacks are Cross Site Scripting, ClickJacking etc. In case of Magecart attacks, if an attacker loads a malicious script from another domain, then the CSP header can be configured to not load any external scripts. But in reality, setting this configuration could be difficult. Thus a well planned policy needs to be written to prevent such attacks. 
</p>

<p>
In Conclusion, as I always say, nothing is 100% secure. And every now and then, new kinds of attacks are coming into picture. It's always better to be aware of the attacks and be ready with all the precautionary measures. We may not be able to avoid cyber attack but we can at least reduce the risk and lower the impacts as far as possible. 
</p>



<b><u>References: </u></b>
<p><a href="https://www.youtube.com/watch?v=fAfRsiBBk-8"> Anatomy of Magecart Attacks </a></p>



