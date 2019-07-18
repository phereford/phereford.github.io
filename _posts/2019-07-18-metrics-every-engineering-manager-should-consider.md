---
layout: post
title: "Metrics Every Engineering Manager Should Consider"
featured-img: metrics-every-engineering-manager
image: "/assets/img/posts/metrics-every-engineering-manager.jpg"
---

# Metrics Every Engineering Manager Should Consider
Individuals who manage engineering teams are often measured by one metric: On
Time Delivery. This means that you complete a certain percentage of your work by
the deliverable date (or by end of a Sprint if using Agile principles). While it
is a good start for measuring the success of your managers, it fails to address
other aspects that these managers have direct influence over: retention and
software quality. The engineering manager will only be successful if the team is
successful. Let’s discuss how we can effectively quantify these measurements.

## On Time Delivery
### Recidivism Rate
This measurement gives you insight into how well your internal software process
is working. The calculation:

Whenever something moves backward in this process, it adds to your percentage.
Whenever tasks move forward, it decreases your percentage. The calculation for
this is  
- SUM(Backward movement of task) / SUM(All task movement)
  
The goal with this metric is variable. Once you establish a baseline (probably
between 10-20%) then you can start monitoring for outliers and have discussions
as to what happened. Some example conversation that might be had:  
- Why did Stakeholders / PMs reject more cards this sprint?  
- Did engineers feel a need to move faster and therefore not test their own code?  
- Were the requirements on the card understood by all those involved? What was
missing?  

This quantitative measurement allows engineering managers insight into how their
team is collaborating and how best to help them move forward together.

### Sprint completion
Defined as the percent of a sprint that is completed and in production. This is
usually set by management and aims for over 80% sprint completion on a sprint to
sprint basis based on task estimates.
  
This metric helps the entire team align around breaking tasks down to their
smallest unit. It also helps the entire team diversify the types of task that
are allocated to the sprint.   

Example: Let’s say that the max effort card to put in a sprint is 21 and you
have 4 engineers. Your rolling 3 week velocity is 84. What are the chances of
success of putting 4 21 point cards into a sprint? Compare that success to 2 21
point cards and a mix of other tasks. Which do you think has a better chance of
success? It is absolutely possible that you will have 4 21 point tasks that are
critical path, which is where measurements and incentives help drive this
decision. If engineers are measured by output/value created and managers by on
time delivery, then 9 times out of 10 they will avoid the 4 21 point card
scenario because it has a higher probability of missing than a well diversified
sprint.  
  
Through this singular measurement we have aligned our product, management and
engineering team in understanding what our output needs to be on a recurring
basis. This informs the business about value created and gives them guidelines
as to how long initiatives take.  
  
### Estimate Health
Let’s all agree that estimates on tasks are based on complexity and not time.
The time it takes to complete 21 1 point cards versus 1 21 point card is not the
same. With that baseline, estimate health essentially applies time bounds to
cards and measures how well the estimate was.  
  
In the example of a sprint with a max task of 21, a 21 point card would take the
full sprint to complete. From that point downward, we apply a linear calculation
for all possible points on tasks as it relates to time. As sprints progress, you
will be able to evaluate what was over estimated and under estimated.  
  
It is important to note that estimates are just that, estimates. It’s not a
promise on delivery, it is an answer given to a problem with known knowledge at
time of discussion without future alterations to the feature set. It is
important, as a business, to get better at estimation and understand key drivers
for what causes estimates to be off. As estimates get better, this gives the
engineering manager a great way to forecast future deliveries.  
  

### Software Quality
#### Test Coverage
Defined as lines of executable code executed during test suite runs divided by
total executable lines of code.  
  
As software and products grow, it becomes incrementally difficult to continue to
execute initiatives AT THE SAME PACE prior to initial launch. This happens due
to code based getting larger, knowledge solos, business requirement changes,
turnover and many other reasons. A healthy test suite, with appropriate use of
the testing pyramid, can help mitigate this as it gives engineers confidence in
incremental value without introduction bugs into production.  
  
Something I have heard in the past regarding this: “Why should an engineering
manager care about this? It seems like it takes time to write these test suites,
time that can just be added to feature work!”  
  
Engineering managers absolutely need to care about this metric. As stated before
this metric gives engineers confidence in building software and deploying
software. With this type of feedback (tests pass or tests fail), your engineers
can be much more productive and maintain feature delivery rates with a healthy
test suite in place. This predictability is an engineering managers dream. As
systems get more complex, it is ever more important to invest in the test suite
to help maintain that predictability.  
  
#### Uptime
Defined as a percentage of availability of a system in a given time frame.
Example: To achieve a 99.9% uptime in a month, you can only be offline for 43
minutes and 49.7 seconds.  
  
As engineers create systems and products, so many metrics are stored and created
to track health of an application. Performance metrics like RPM (requests per
minute), error rates and more are all valuable. Engineers absolutely care about
these metrics because it effects their ability to support the product. From a
managers perspective, these are less important to uptime. Uptime gives managers
insight into how the overall system is acting from a 30,000 foot view.  
  
The reason to track this as a manager is to ensure that your product is adding
the value you expect and is consistently available for your customers.  
  
#### Code Styles
An underrated tool for managing code quality are standard style guides for each
language being used at your organization. By standardizing what your code will
look like, you end up removing _much cognitive load_ on the individuals building
the feature and those that code review the feature. Here is a small example:
``` ruby
class Foo
  def bar
    return if baz?
    return unless boo?

    "Ping!"
  end
...
end
```
``` ruby
class Foo
  def bar
    if baz?
      "Ping!" unless boo?
    end
  end
...
end
```
It will vary from person to person and team to team, but one of these is easier
to read. *It does not matter which is easier to read* so long as the
team collectively agrees on which is easier to read and enforce a rule in their
style guide to keep it.  
  
While rules are all well and good, you need to automatically enforce these
rules. This is where linters come into play. Linters should be run
locally and when pull requests are open.  
  
### Retention
#### Employee NPS
This is defined as how engaged, happy, and motivated your team is on a scale of
1-10.  
  
Managers should be performing 1-1 meetings with individuals they are managing.
These 1-1 meetings can surface issues that are happening in near real time.
These issues are non quantifiable but are a great indicator to how happy and
productive the team is.   
  
A good proxy to measure this is NPS. NPS stands for net promoter score. Most
companies do measure this internally on a semi annual or annual basis. From a
managers perspective, this is useless data because it is way too infrequent to
make any decisions. Instead, a manager should own their team’s NPS score and
survey EVERY WEEK. This won’t take but 2-5 minutes of time from each member on
your team and over time you can catch trends and problems faster as they arise.
From a company standpoint, if a manager helps their team, grows their team and
is supportive that will be reflected in the NPS. If your manager is just pushing
you team to hit deadline after deadline, this will also be shown in the NPS score
in a negative fashion.  
  
This helps managers collaborate with other managers to find better ways of
engaging their team and better ways of supporting their team. This is ultimately
why managers need to be measured by more than just on time delivery.  
  
## Summary
We covered a lot of different metrics and use cases for them. The basic
construct for these measurements are to analyze team behavior that a manager has
influence over. These measurements help organizations identify behaviors that
create value and add to the predictable release of value. These measurements are
exactly what the mission of every engineer manager should be. 

##### Photo Attribution
[Photo by Lukas from Pexels](https://www.pexels.com/photo/macbook-pro-beside-papers-669619/)
