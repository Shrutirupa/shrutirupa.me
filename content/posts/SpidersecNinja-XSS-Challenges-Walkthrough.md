---
title: "SpidersecNinja XSS Challenges Walkthrough"
date: 2020-07-23T03:06:08+05:30
draft: false
---

<b> Introduction: </b>
<p>
XSS challenges have always been tricky kinds of challenges, especially the ones where your normal payload would never work and you have to go through different kinds of tags, attributes, and event handlers to craft your XSS payload. 
DOM-based XSS challenges are no different, the only difference is, you need to analyze a bit more to understand the kind of payload to be crafted to execute it. 

Let’s get an overview of it.
DOM stands for Document Object Model which is used to make any changes in the DOM of the browser. DOM works according to the user input which is the source and the element/object which consumes our input and performs actions accordingly is called the sink.
So, if the user input contains the payload, and if the user input is consumed by a sink then the application might be vulnerable to DOM-based vulnerabilities.

 
In this article, I will be writing about my approach towards finding and exploiting DOM-based XSS by solving the labs here: https://spidersec.ninja/labs/index.html </p>

<p> Let’s get started: </p>

<img src="/images/image1.png" />

<p> We have a total of seven challenges and we will analyze each of them one by one. :) </p>

<b> Challenge 1: </b>

<img src="/images/image2.png" />

<p> Here, we have an input field. Let’s start by analyzing the input field first. I will add “shruti” and observe the reflection. </p>

<img src="/images/image3.png" />

<p> We see that the string “shruti” is getting reflected. Let’s review the source code to find out the reflection point.
</p>
<img src="/images/image4.png" />

<p>The string “shruti” is not reflected in the source code. Also, we see the use of document.getElementById() , so it seems to be using DOM. Let’s Chrome DevTools and analyze the code again. In Chrome, select the string “shruti”, right-click and open inspect element. Then click on Sources. Similar steps can be followed on any other browser</p>

<img src="/images/image5.png" />

<p> Click on the line number 36 as shown in the screenshot above to set a breakpoint on it so that when the application hits this line it will pause its execution and wait for us to take action on it which can be used to step through each function calls after this line </p>
<p> Wait!! Why line 36??? </p>
<p> Because, while analyzing the code, we observed that this line is the one which is asking for our input via the document,getElementById(). Now we need to figure out which function is consuming our input </p>

<p> You should see a red circle in front of the line which indicates the breakpoint</p> 

<img src="/images/image6.png" />

<p>Next, we use the step function as marked in the image below to see the next steps which helps us to analyze and understand the code flow further. </p>

<img src="/images/image7.png" />

<p> And on clicking on the step function... </p>

<img src="/images/image8.png" />

<p> Here we will see our string “shruti”. So here we find our input source which as suspected is the document.getElementById(). </p>

<p>Let’s move to the next step and see what happens.</p>

<img src="/images/image9.png" />
Step 1:

<img src="/images/image10.png" />
Step 2:

<img src="/images/image11.png" />
Step 3:

<p>The html variable on line 40 is responsible for reflecting our input on the browser because of innerHTML. So the innerHTML is our sink here and we know if our input consumed by sink it can possibly be vulnerable to DOM-XSS. So, let’s try a simple payload in the input. </p> 
<p>But wait a minute, script tags do not get executed in innerHTML. So, let’s add our payload with an img tag, which will be <img src="/images/image12.png" /> </p>

<img src="/images/image13.png" />

<p> It seems that the img tag is getting executed but our alert function is not working. Let’s analyze our payload again in the debugger. </p>

<img src="/images/image14.png" />

<p> Let’s click on the step button and see the next step.</p>

<img src="/images/image15.png" />

<p>Here, we see that on line 37 the round brackets () are getting filtered out by js_filter0. So we need to come up with a payload without the round brackets. Let’s try this payload now <img src="/images/image16.png" /> </p>

<img src="/images/image17.png" />

<p> And boom we are done. We solved our first challenge :) </p>
We now understood how to use a debugger to analyze our code and look for the source and sink. We will follow similar steps throughout this article to solve the rest of the challenges.


<b> Challenge 2: </b>

<img src="/images/image18.png" />

<p>In this challenge, we will perform the same steps as above to solve it.
While debugging, we see that this challenge also uses document.getElementById as the source and innerHTML as the sink. </p>

<img src="/images/image19.png" />

<p>We again enter our string “shruti” and analyze the code in the debugger, as shown in the screenshots below. </p>

<img src="/images/image20.png" />

<img src="/images/image21.png" />

<p> So, in this challenge, we observe that the spaces are being filtered on line 37 in the js_filter1 variable. </p>

<img src="/images/image22.png" />

<p> So, on adding the normal payload - <img src="/images/image23.png" />  gives the following response. </p>

<img src="/images/image24.png" />

<p> And this is how it looks like in the debugger.  </p>

<img src="/images/image25.png" />

<p> As we can see, the spaces are getting filtered over here, so we will have to use ta payload without spaces. </p>
<p> Let’s try - <img src="/images/image26.png" /> </p>

<img src="/images/image27.png" />

<p> And challenge 2 is done as well… :)  kudos to us :) </p>

<b> Challenge 3: </b>

<img src="/images/image28.png" />

<p> Since we already understood how to analyze a DOM-based XSS with the help of debugger, we will directly jump to the step where we are adding our normal payload which is - <img src="/images/image12.png"> </p>

<img src="/images/image29.png" />

<p>Let’s check in the debugger. </p>

<img src="/images/image30.png" />

<p> So, confirm, prompt, alert, write, open all of these keywords are getting filtered out but we can still execute javascript. 
What if we still want to see the popup? </p>
<p> Let’s try to analyze and understand this </p>
<p>We will play with the “alert” keyword. Putting an “alert” keyword does not work as it is getting filtered out, we can use alternative ways such as ALERT in all capitals and see if it works.  </p>

<img src="/images/image31.png" />

<p> Well!! It did not. It seems like the regex is strictly looking for the alert keyword </p>
<p> Let us try alalertert(1) instead of normal alert(1). Since the “alert” word is getting filtered out, we are using alert in between al and ert, so when the alert from the middle gets filtered out, we will have alert(1) again and as we can see in the code, there is no further check. So, let’s try this payload then - <img src="/images/image32.png" /> </p>

<img src="/images/image33.png" />

<p> We added our payload, and it did not work. Let us again check the debugger and analyze this further. </p>

<img src="/images/image34.png" />

<p> Our alalertert seems to be working fine. Let’s go to the next step and see. </p>

<img src="/images/image35.png" />

<p>If we observe, we will see that this time our payload is getting inside the tag attribute and for our payload to work, we will have to end this tag first to break the current context. So, our payload for this will be: <img src="/images/image36.png" />
</p>
<p>Let’s try this:</p>

<img src="/images/image37.png" />

<p> And it worked... :D </p>	
<p> Amazing!!! </p>

<b> Challenge 4: </b>

<img src="/images/image38.png" />

Analyzing the code as above, we will try adding - <img src="/images/image12.png" />  into the input field. 

<img src="/images/image39.png" />

<p>The img tag is getting executed but not the alert part. Let’s check in the debugger. </p>

<img src="/images/image40.png" />

<p> So, the round brackets ‘(‘ and the closing angular bracket '>' are being filtered out. If we remember, even in our first challenge, the round brackets were getting filtered out, so let us use `` instead of ().
And hence, our payload becomes <img src="/images/image41.png" />
But in this case, the ‘>’ also is filtered out. </p>
<p> Let’s not add '>' in the end and see if it gets executed. </p>

<img src="/images/image42.png" />

<p> No, it is not getting executed. Let us add a comment at the end of the payload which will look something like this:  <img src="/images/image43.png" />. Here we are basically tricking the browser to think that the rest of the code is a comment and that it should execute the code before the comment as it is. </p>

<img src="/images/image44.png" />

<p>And we did it again. :) </p>

<b> Challenge 5: </b>

<img src="/images/image45.png" />

<p>Here is our challenge 5 and let’s start with analyzing the code with the help of the debugger again. :D But this time we observe something at the very first step. Let’s write “shruti” into our input field and analyze the code in the debugger.</p>

<img src="/images/image46.png" />

<p>Here, we can observe that there is an img tag in the code and it is getting executed. Let’s analyze this.</p>

<img src="/images/image47.png" />

<p> As we can see in the screenshot above, our input is already in the img tag. Also, we observe that the () and <> are getting filtered out, so we can craft our payload in this way- <img src="/images/image48.png" /> </p>

<p>So, let’s try our payload. </p>

<img src="/images/image49.png" />

<p>But our payload did not work. Let’s analyze the code further.</p>

<img src="/images/image50.png" />

<p>Let’s comment out the rest of the part and thus, our payload becomes - <img src="/images/image51.png" /></p>

<img src="/images/image52.png" />


<p> And we did it again. :)  </p>

<b> Challenge 6: </b>

<img src="/images/image53.png" />

<p> Following the same steps as above, we add our string and analyze it in the debugger to understand what is happening. </p>

<img src="/images/image54.png" />

<img src="/images/image54.png" />

<p> From the above code, we can see that almost every tag is filtered out, so adding img within img (Eg: imimgg) will also not help as there are a lot of checks involved. 
But if we observe carefully, we can still bypass the filter but using the img tag in capital letters. </p>

<p> Also () and >  are getting filtered out. </p>

<img src="/images/image56.png" />

<p>And thus, our payload becomes - <img src="/images/image57.png" /> </p>

<p> We added // in the end, to comment out everything after our payload. </p>

<img src="/images/image58.png" />

<p> And it worked too. :D </p>

<p> Let’s analyze the final challenge :)  </p>

<b> Challenge 7: </b>	

<img src="/images/image59.png" />

<p> Let’s follow the above steps and analyze this challenge. :) </p>

<p> On adding the <img src="/images/image60.png" /> , we receive the following output. </p>

<img src="/images/image61.png" />

<p> As we see the screenshot below:</p>

<img src="/images/image62.png" />

<p>The code is replacing every character that we use for crafting our payload. But if we observe carefully, there is something very interesting there - unescape(html) </p>

<img src="/images/image63.png" />

<p>I, then, googled for the unescape function to understand what it does. 
I referred to <a href="https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_unescape"> this </a> link, to analyze the function. </p>

<img src="/images/image64.png" />

<p>Here, we see that whenever we enter a string, and if it goes through the escape function it gives us output in an encoded format. And the unescape function, then url decodes it.
Thus, if we put our payload in the same encoded format, it may get decoded by the unescape function used and also won’t get filtered out. </p>

<p> So, we craft our payload as  - <img src="/images/image65.png" /> </p>

<img src="/images/image66.png" />

Putting our payload into the input field: 

<img src="/images/image67.png" />

<p> And it worked. :D </p>
<p> We are done with all the challenges. </p>
<p> I hope you all learned something and let me know if you have any doubts or queries.  </p>

<b> <u> Resources: </u> </b>

<p> <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model"> Document Object Model (DOM)  </a>  </p>
<p><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/unescape"> unescape() </a></p>

<p><a href="https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/">How Browsers Work: Behind the scenes of modern web browsers</a></p>
<p><a href="https://github.com/s0md3v/AwesomeXSS"> AwesomeXSS </a></p>
<p><a href="https://github.com/RenwaX23/XSS-Payloads/"> XSS-Payloads </a></p>

