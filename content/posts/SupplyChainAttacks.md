---
title: "SupplyChain Attacks"
date: 2021-06-13T01:36:35+05:30
draft: false
---

<p>
Organizations are constantly under target of cyber attacks and data breaches. New attacks keep coming. Sometimes the older attacks end up working and other times, these older attacks get some modification to perform a zero-day to compromise an organization. In today’s post, we will learn about a very interesting attack - the SupplyChain attack. 
</p>
<p>
You can check my previous blog posts <a href="https://shrutirupa.me/posts/">here </a> where I discussed some good security jargons and attacks that a security professional should be aware of.
</p>
<p>
While comprehending Supply Chain Attacks, we will take a sneak peek at two organization’s attack scenarios.. So, let’s get started. :) 
</p>
<p>
Let us first understand what a SupplyChain means before we start.
</p>
<p>
A supply-chain is a process of making commercial products from scratch including the supply and manufacturing of the materials, till the selling of them. Every stage is important and counted in a supply chain process and hence the name. 
</p>
<p>
In supply Chain every step is critical hence compromising any stage leads to supply chain attacks.
The attacks focus on the less-secure elements in the process. This is an universal attack scenario for organizations. Most of the time, the attackers tamper with the manufacturing processes. 
</p>
<p>
APTs play a very vital role here. You can learn about APTs from <a href="https://shrutirupa.me/posts/advanced_persistent_threats/ ">here</a>. For now, we can understand that APTs are Advanced Persistent Threat which looks for the weakest link in a product or network in an organization to sit over there and gradually take control of the active directory or other admin domains. SupplyChain attacks generally begin from here.
</p>
<p>
There are some infamous victims here: British Airways, Solarwinds, Microsoft exchange server
</p>

<p>
Now let’s dive a bit deeper into two infamous supply chain attacks and try to understand what happenes. 
</p>
<p>
<b>Solarwind attack: </b> </p>
<p>
We all are aware of the very well-known Solarwinds Supply chain hack that happened recently.
First of all, let us understand what Solarwind is?  Solarwind is an American-based company that develops software to help companies to maintain their IT infrastructure like networking. The company has various products used for monitoring networks. The attackers targeted the Orion System and inserted a malicious code in there, with the help of a supply chain attack. They made use of the Sunburst backdoor that was a digitally signed plugin of the Solarwinds Orion plugin, which is called SolarWinds.Orion.Core.BusinessLayer.dll. The plugin communicates to the third-party servers through HTTP. The backdoor remains quiet for about 2 weeks before performing further attacks like executing commands, transferring files, and many more. It keeps the information to be used later for future attack stages.
</p>
	<p>
This is how the attackers found the weakest link to set up the backdoor. This led to the supply chain attack that further affected those companies which used the Solarwind product for their use. 
</p>
<p>
Let us understand another scenario of  a supply chain attack.
</p>
<p>
<b>Github attack: </b>
</p>
<p>
Open source projects are no way more secure than any commercial ones. A Supply chain attack has affected one GitHub project too that targeted the NetBeans IDE repositories. The malware used was Octopus Malware which was designed to infect the NetBeans projects.
</p>
<p>
The malware would use a cache.dat file to infect the nbproject directory. And every time the project is built, it infects the .class and the jar files which are generated inside the jar file during the build process. Malwares  don’t just infect the files , they also create  a backdoor  to the system and communicate with the command and control server. This command and control server can build communication whenever it wants to and execute commands and move files as it wants. 
</p>
<p>
To conclude, nothing can be 100% secure but we can always take precautions to reduce the risk. We will have to keep monitoring and patching each component of the tool or project so that any weak link can be taken care of before getting under the control of a malicious user. We can always learn from the previous examples and reduce the risk as far as possible. 
</p>


<b><u>References: </u></b>
<p><a href="https://www.varonis.com/blog/solarwinds-sunburst-backdoor-inside-the-stealthy-apt-campaign/">Solarwinds Sunburst Backdoor Inside the Stealthy Apt Campaign</a></p>
<p><a href="https://portswigger.net/daily-swig/how-octopus-scanner-malware-attacked-the-open-source-supply-chain">how Octopus Scanner Malware attacked the Open Source SupplyChain</a></p>
<p><a href="https://cycode.com/blog/beyond-solarwinds-the-octopus-scanner-supply-chain-attack/">beyond Solarwinds the Octopus Scanner SupplyChain Attack</a></p>
<p><a href="https://www.hstoday.us/subject-matter-areas/cybersecurity/new-technical-details-about-sunburst-backdoor-malware/
">new technical details about Sunburst Backdoor Malware</a></p>
<p><a href="https://www.youtube.com/watch?v=4onCKbtWszQ">The Evolution of SupplyChain Attack</a></p>







