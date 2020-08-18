---
layout: post
title: "Assigning Blame in Engineering is Absurd"
featured-img: photo-of-man-pointing-his-finger
image: "/assets/img/posts/photo-of-man-pointing-his-finger.jpg"
---

It's 9am, Monday morning. You set your bag down, take a sip of coffee, power
your laptop and open your email. The first email you see has the title "URGENT:
EVENTS NOT COMING THROUGH TO OUR PLATFORM". Okay...not the best Monday start.
You quickly do some analysis and understand how long this has been happening,
check git history, talk to coworkers. You decide it's a good idea to respond
with the following:  
> Hey there! Thanks for bringing this to our attention! We have looked at all
the culprits here and we are uncertain if this is an issue with our third party
vendor. Let's give it one more day, as this is not business critical, to make
sure it isn't just internet gremlins.  
  
It's 9am, Tuesday morning. You set your bag down, take a sip of coffee, power
your laptop and open your email. The first email you see has the title: "RE:
URGENT EVENTS NOT COMING THROUGH TO OUR PLATOFRM". Sigh.  

> The events did not come again! THIS IS BUSINESS CRITICAL! I WANT TO KNOW WHO
IS RESPONSIBLE!  
  
Okay...this escalated quickly. After two more hours of understanding what happened,
and fearing for your job at this point, you uncover what the cause of the issue
is! On Friday, someone deployed some code (that passed CI, passed code review,
and was collaborated on) in a subsystem. You quickly fix it, disseminate to the
whole engineering team via a postmortem what the cause was. A senior engineer on
your team takes it a step further and builds a pre-check git hook that ensures
all code can be executed prior to committing to the repository. Finally, you can
respond to the email and bring down the anxiety.  
  
> Hey there again! We were finally able to get to the bottom of it! We even
implemented additional checks and balances to make sure this issue never happens
again. I apologize for the disruption this caused in your daily work, but I
assure you, this will not happen again.  
  
You finally turn to your daily tasks to get back into feature development...
until your boss comes and suggests to have a sit down! You walk in, as a Software
Engineer, and seated there are 2 Vice Presidents and the individual that raised
the alerts. Mind you, everyone in this room know engineerings processes around
Continuous Delivery, blameless culture, etc. First question to field:  

```
Stakeholder> I want to know who is responsible for this outage!  
You> Like I said in my emails, this was the issue at hand. This is what we have
done to prevent this in the future. What does it matter who wrote the code?  
Stakeholder> It matters to me! I want to hold them accountable?  
You> Again, you know our processes. That feature was paired on, passed code
review from two senior engineers, passed out automated testing and was auto
deployed. Why does it matter who wrote the code?  
VP> I don't understand why you won't just tell us who wrote the code.  
You> I really hate to sound like a broken record here, but it is a process
issue. You see how reliable our systems are. Bugs happen. Failures happen. We
do our best, _from a process standpoint_, to prevent these from being
catastrophic or disruptive to the business.  
Other VP> Just tell him who wrote the code.  
You> /smh
```

The above anecdote, while slightly exaggerated, is a true tale. In today's
thought leadership bubbles, there is a very important reason as to why there
has been a shift to having blameless cultures and creating
psychologically safe environments where mistakes are welcomed and make teams
stronger. That very reason is illustrated in the above anecdote. Where exactly
is the point of failure? Is it with the engineer that wrote the code? The
collaborator who paired with said engineer? The two engineers that code reviewed
that bug? Our automated test suite for not catching it? Are the product mangers
accountable because their tasks were not fully baked?
  
The answer to each of those questions is a resounding **NO**. The issue at hand
here is we had a lapse in process that did not catch a bug in a subsystem
before it happened. The best part about this particular team was that as soon
as that post mortem was published and consumed by the engineering team, a senior
engineer within two hours had a robust, non-intrusive way to ensure this
particular issue will never happen again. He did this absolutely unprompted!  
  
You are one team, within the department and outside of the department. Everyone
is accountable as a whole and it's absurd to lay blame at the feet of
a singular individual when bugs happen. Everything in organizations is a team
effort, in failure and success.  
  
Work together, take care of each other, and have some fun.

##### Photo Attribution
[Photo by Ketan Kumawat](https://www.pexels.com/photo/gray-wooden-bridge-724955/)
