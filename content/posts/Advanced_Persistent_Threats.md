---
title: "Advanced Persistent Threats"
date: 2020-12-13T00:36:57+05:30
draft: false
---
<p>
Working in a security domain for over 2 years, one thing that I keep realizing each day is nothing is 100% secure and we can never deny this fact. The more we strive for the security of an organization’s perimeter or boundary, the less we think about the internal network scenario of the same. Sometimes, some attacks, especially the zero-days, have already penetrated through the organization’s network and are sitting in the internal network, extracting the sensitive information of the organization one by one, and we are still unaware of it. And this leads us to today’s post on “Advanced Persistent Threats”.
</p>
<p>
Let's break down the terminologies and understand the meaning in details:
</p>
<p>
Advanced - something which is of a higher level
</p>
<p>
Persistent -  something which has been lasting for a long time
</p>
<p>
Threats - something which means danger and we should be aware of
</p>

<p>
So, together what we can understand is Advanced Persistent Threats or APT are attack scenarios where an enterprise is already compromised and the malicious entity is present within the enterprise for an extended time without getting detected. 
Since the goal of this malicious entity is to sit in the compromised enterprise for an extended period, then it must have been planned before and it might be specific to the particular enterprise. Thus, an APT can be considered as one sophisticated kind of attack, very well planned against an organization to satisfy some unpleasant goals. 
</p>
<p>
APTs do make use of social engineering to get their works done. So, let’s understand the steps to get a rough idea of how this works: 
</p>
<p>
1. The first step happens through malicious links in the emails, or malware that were shared, so once these links are clicked or once the malware gets installed, we are one step towards compromising the network. Now, most of the existing malware might get detected by the antiviruses, but as the attack is well planned so a customized and zero-day kind of attack might be chosen to compromise the network. 
</p>
<p>
2. The malware, once in the network, would want to spread throughout the network for further access and also need to communicate with command and control(C&C) servers for further damage. 
But what are C&C servers?
These are nothing but systems, under the control of the attacker to send commands to the compromised machines. Thus, if the enterprise’s network is already compromised, creating a connection with the C&C servers, allow the attackers to perform any command to affect the enterprise further.
</p>
<p>
3. As has already been said, the malware will try to spread but in such a calculated way so that it doesn't get detected that easily. It may try to find various connection points so that if one of such points gets closed, it can remain there. 
</p>
<p>
4. At this moment, the entire network is already compromised. Now the attacker starts to achieve its goal, which is a data breach. It starts looking for usernames, passwords, and trying different attack scenarios to find sensitive information, and hence the network comes almost under the control of the malicious entity.
</p>
<p>
5. The logs or any evidence of the APT is removed from the logs, and also the APT leaves but the network remains compromised leaving a backdoor in the network so that the attacker can come back and forth whenever required, hence C&C servers continuing their work. 
</p>
<p>
The above process, quite approximately, explains, why we need to maintain and be aware of the security risks, both externally and internally. This is also one reason why we are heading towards Zero Trust Security Model. I did talk about the topic in my blog here, you can check it out.
</p>
<p>
While concluding that, one thing that we can always take care of is “think before you click”. If it is not from an ascertained source, we don’t need to click entertain it, as this may not only result in compromising just one’s system but also into compromising the entire enterprise network. 
</p>