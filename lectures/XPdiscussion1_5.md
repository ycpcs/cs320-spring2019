---
layout: default
title: "XP Discussion Topics, Chapters 1-5"
---

Chapter 1: What is XP?
============

Excerpted from "Extreme Programming Explained" by Kent Beck.  The author states that:

XP is focused on the excellent application of:

-	Programming techniques
-	Clear communication
-	Teamwork

XP includes:

-	A PHILOSOPHY of SW development based on the the VALUES of communication, feedback, simplicity, courage, and respect.
		
-	A body of PRACTICES proven useful in improving SW development.  The practices complement each other, amplifying their effects.  They are chosen as expressions of the VALUES.
		
-	A set of complementary PRINCIPLES, intellectural techniques for translating the VALUES into PRACTICE, useful when there isn't a practice handy for your particular problem.
		
-	A COMMUNITY that shares these VALUES and many of the same PRACTICES.
		
XP is a path to excellence for people coming together to develop SW.  It is distinguished from other methodologies by:

-	Short development cycles, resulting in early, concrete, and continuing feedback.
	
-	An incremental planning approach, which quickly comes up with an overall plan that is expected to evolve through the life of the project.
	
-	The ability to flexibly schedule the implementation of functionality, responding to changing business needs.
	
-	Reliance on automated tests written by programmers, customers, and testers to monitor progress of development, to allow the system to evolve, and to catch defects (bugs) early.
	
-	Reliance on oral communication, tests, and source code to communicate system structure and intent.
	
-	Reliance on an evolutionary design process that lasts as long as the system lasts.
	
-	Reliance on the close collaboration of actively engaged individuals with ordinary talent.
	
-	Reliance on practices that work with both the short-term instincts of the team, and the long term interests of the project.
	
The author describes XP this way:

-	**XP is lightweight.**  In XP, you only do what you need to do to create value for the customer.  You can't carry a lot of baggage and move fast.  However, there is no freeze-dried SW process. The body of technical knowledge required to be an outstanding team is large and growing.
	
-	**XP is a methodology based on addressing constraints on SW development.**  It does not address project portfolio management, financial justification of projects, operations, marketing, or sales.  XP has implications in all of these areas, but does not address these practices directly.  Methodology is often interpreted to mean "a set of rules to follow to guarantee success."  Methodologies don't work like programs.  People aren't computers.  Every team does XP differently with varying degrees of success.
	
-	**XP can work with teams of any size.**  XP has been put into use in a wide range of projects and has been successful for both large and small projects and teams.  The values and principles behind XP are applicable at any scale.  The practices need to be augmented and altered when many people get involved.
	
-	**XP adapts to vague or rapidly changing requirements.**  XP is still good for this situation, which is fortunate because requirements need to change to adapt to rapid shifts in the modern business world.  However, teams have also successfully used XP where requirements don't seem volatile, like porting projects.

The author claims that XP addresses risk at all levels of SW development:

-	**Schedule slips:** XP calls for short release cycles, a few months at most, so the scope of any slip is limited.  Within a release, XP uses one-week iterations of customer-requested features to create fine-grained feedback about progress.  Within an iteration, XP plans with short tasks, so the team can solve problems during the cycle.  Finally, XP calls for implementing the highest priority features first, so any features that slip past the release will be of a lower value.
	
-	**Project cancellation:** XP asks the business-oriented part of the team to choose the smallest release that makes the most business sense, so there is less that can go wrong before deploying, and the value of the SW is greatest.
	
-	**System goes sour:** XP creates and maintains a comprehensive suite of automated tests, which are run and rerun after every change (many times a day) to ensure a quality baseline.  XP always keeps the system in a deployable condition.  Problems are not allowed to accumulate.
	
-	**Defect rate:** XP tests from the perspective of both programmers writing tests function-by-function and customers writing tests program-feature-by-program-feature.
	
-	**Business misunderstood:** XP calls for business-oriented people to be first-class members of the team.  The specification of the project is continuously refined during development, so learning by the customer and the team is reflected in the SW.
	
-	**Business changes:** XP shortens the release cycle, so there is less change during the develpment of a single release.  During a release, the customer is welcome to substitute new functionality for functionality not yet completed.  The team doesn't even notice if it is working on newly discovered functionality or features defined years ago.
	
-	**False feature rich:** XP insists that only the highest priority tasks are addressed.
	
-	**Staff turnover:** XP asks programmers to accept responsibility for estimating and completing their own work, gives them feedback about the actual time taken so their estimates can improve, and respects those estimates.  The rules for who can make and change estimates are clear.  Thus, there is less chance for a programmer to get frustrated by being asked to do the obviously impossible.  XP also encourages human contact among the team, reducing the loneliness that is often at the heart of job dissatisfaction.  Finally, XP incorporates an explicit model of staff turnover: new team members are encouraged to gradually accept more and more responsibility, and are assisted along the way by each other and by existing programmers.
	
The author then states a collection of assumptions that XP makes:

-	XP assumes that you see yourself as part of a team, ideally one with clear goals and a plan of execution.
-	XP assumes that you want to work together.
-	XP assumes that change can be inexpensive using this method.
-	XP assumes that you want to grow, to improve your skills,and to improve your relationships.
-	XP assumes that you are willing to make changes to meet those goals.
		
Finally, the author summarizes XP this way:

-	XP is giving up old, ineffective technical and social habits in favor of new ones that work.
-	XP is fully appreciating yourself for total effort today.
-	XP is striving to do better tomorrow.
-	XP is evaluating yourself by your contributions to the team's shared goals.
-	XP is asking you to get some of your human needs met through SW development.

**We will first discuss XP (as described above) in relation to the Waterfall Model example to be presented in the previous lecture, assuming that XP could be applied to that project.**

**The author makes a lot of claims about XP, as well as states many qualities that XP possesses, including addressing human factors.  He makes it sound like a lifestyle.  Discuss your reaction to what the author has to say in the first chapter about XP?**

The author makes this statement about estimates and expectations, "If you have six weeks to get a project done, the only thing you control is your own behavior.  Will you get six weeks' worth of work done, or less?  You can't control others' expectation.  You can tell them what you know about the project so that their expectations have a chance of matching reality.  My terror of deadlines vanished when I learned this lesson.  It's not my job to "manage" someone else's expectations.  It's their job to manage their own expectations.  It's my job to do my best and to communicate clearly."

**Who determines how much work is "six weeks' worth of work"?  What if your manager (or your professor) imposes unreasonable/impossible deadlines on you (and/or your team)?  How do you put the author's statement into practice?  There is an inherent conflict here, and imbalance of "power", skewed far to side of the manager.  What do you do to deal with it?  How should a team that is responsible for setting its own estimates deal with the rejection of those estimates?**

Chapter 2: Learning to Drive
============

Chapter 2 is all about accepting and adapting to change.  The author states, "everything in SW changes.  The requirements change.  The design changes.  The business changes.  The technology changes.  The team changes.  The team members change.  The problem isn't change, because change is going to happen; the problem, rather, is our inability to cope with change."
	
XP follows the premise that customers, internal or external, drive change, and that they should not only be "allowed" to drive change, but should be encouraged to drive change, and that they are an integral part of the XP team.	

CHAPTER 3: Values, Principles, and Practices
============

The author treats programming as a social skill, at times.  He discusses how principles are the bridge between values and practices.

**What does he mean by "values", "principles", and "practices"?**

CHAPTER 4: Values
============

The author states that XP embraces the following 5 values:

-	Communication
-	Simplicity
-	Feedback
-	Courage
-	Respect
	
**How do you portray those values in your SW development, or other coursework?**
	
**COMMUNICATION:** I'll give an example from my work experience.

**How do you see communication being used in your group project development?**

**SIMPLICITY:** I'll give an example from my work experience.

**How do you go about simplifying your code (your solution to the problem)?**

**FEEDBACK:** The author states that XP strives to generate as much feedback as possible.

**What constitutes feedback?  How do you encourage/generate feedback?**

**COURAGE:** The author states that "courage" is effective action in the face of fear.

**Give some examples of courage that you have exhibited during you collegiate career - times when you have confronted and conquered your anxiety/fear.**

**RESPECT:** I'll give an example from my work experience.

**Identify instances of respect and disrespect that you've encountered during your collegiate career.  This could be from students, professors, or from a coop experience.  Please don't use real names.**

**OTHERS:**

**Are there any other values you think are essential to successful SW development in a team environment?**

CHAPTER 5: PRINCIPLES
============

The author states that XP is guided by the following principles:

-	Humanity
-	Economics
-	Mutual Benefit
-	Self-Similarity 
-	Improvement
-	Diversity
-	Reflection
-	Flow
-	Opportunity
-	Redundancy
-	Failure
-	Quality
-	Baby Steps
-	Accepted Responsibility
	
**From a team-oriented SW development standpoint, order those from highest to lowest in terms of importance.**
	
**HUMANITY:**  The author states the following as being essential in order to be a good developer:

-	Basic Safety - freedom from hunger, physical harm,and threats to loved ones.  Fear of job loss threatens this need.

-	Accomplishment - the opportunity and ability to contribute to their society.

-	Belonging - the ability to identify with a group from which they receive validation and accountability and contribute to its shared goals.

-	Growth - the opportunity to expand their skills and prespective.

-	Intimacy - the ability to understand and be understood deeply by others.
	
**What has your developmental environment been like while you've been at York College - collaboration, socialization, friendships, partnerships?  In what ways do you expect those areas to carry over into your career.  What is essential to you for a happy, successful, and fulfilling career?**
	
**The author clearly states what he feels should and shouldn't be discussed/shared with team members.  He says that private matters should remain private and not revealed to the team.  On the other hand, you will spend a lot of time working closely with the people on your team - many will become friends, and even close/lifelong friends.  What is your reaction to what the author has to say about those types of discussions?**

**ECONOMICS:** Essentially, all commercial SW development comes down to money - how much the ROI (return on investment) will be.

**How do you perceive that statement will affect/drive your career decisions?**

**MUTUAL BENEFIT:** The author implies that it is generally not worthwhile to invest time in documenting for the future - future team members, future features, future releases  That the documentation should be implicit in the code, the tests, the comments, the names.

**What is your reaction to that?  Can you think of examples that would require more explicit documentation - for instance, how do you convey information to members of an XP team who aren't developers?  How do you keep record of team decisions - how do you pass on designs to new team members?**

**SELF-SIMILARITY:** The author states that the team should always be on the lookout for code and processes that are similar - and can be used at different scales.  If you can abstract functionality from different parts of your design into common code - then only one instance of the code must be maintained and tested.

**IMPROVEMENT:** The author states that the team should always be seeking ways to improve the code.  It is not possible to come up with a perfect design, or perfect processes - but it is possible to continue to perfect the design, the code, and the process.  XP calls for excellence through improvement.

**If the team is constrained for time, but comes across an improvement, how does it decide whether to spend time refactoring the code, implementing the improvement?  How do they justify that?**
	
**How do you feel about the phrase, "best is the enemy of good enough"?  Under what circumstances is "good enough" sufficient - meaning that even an obvious improvement should not be implemented?**

**DIVERSITY:** With a diversity of knowledge, skills, and experience, comes a diversity of opinion on approaches and solutions.

**How can this diversity be utilized in a positive way?  How do you propose to reach a common approach/solution?**

**REFLECTION:** Honest reflection (review) of one's individual work (successes and failures) as well as that of the team, leads to improvement - both by sharing what has worked, and by recognizing and sharing mistakes, rather than hiding them (learning from one's own mistakes, as well as the mistakes of others).

**FLOW:** The author states that more smaller chunks of development are better than fewer large chunks of development.  The team see a steady flow of progress towards success.  Flow would be when you finally understand the assignment, have assembled it in your head, and can make steady, uninterrupted progress towards it - think Mandelbrot in CS201.

**How do you feel at the beginning of an assignment, and how does that change over time as you finally understand the problem and know how to make progress?  How have you felt when you have just completed a tough assignment, and then had to start on a new and completely different asignment right away?  Would you prefer more smaller assignments, or fewer bigger assignments?**

**OPPORTUNITY:** The author states that you should learn to see problems as opportunities for change - continue learning beyond just enough to get by with solving the problem.  Problems should be used as opportunties for learning and improvement, rather than viewed only as "survival".

**How do you identify opportunity in a problem?  Think about the upcoming group and individual projects.**

**REDUNDANCY:** The author states that critical problems in SW development should be solved in multiple ways.

**I also emphasized that approach in CS201.  Why continue looking for solutions after one is identified?**

**FAILURE:** We learn from our failures until we reach success.

**How have you learned from failure in CS201, or some other engineering course?**

**QUALITY:** The author states that projects don't go faster by accepting lower quality - a poor design, more "acceptable" defects, less testing.  This is also my experience - that lack of quality comes back to haunt you late in the project, or sucks time away from you after a release.

**Define quality in terms of you own SW development experience.  What does quality mean to you?**

**BABY STEPS:** Take many small steps in development, rather than a few larger steps. Complete small chunks more quickly and integrate them into the code base.

**Reflect on your SW development efforts in CS101 and CS201.  Did you ever experience writing too much code, and then struggling to get it to work?  When you worked on Klondike, it was a large, complex project, but was broken into small testable pieces.  How did that development go for you?**

**ACCEPTED RESPONSIBILITY:** The author states that no one can assign responsibility to you - it is up to you to accept responsibility.  He gives an example that if a team member signs up for a task, they also accept for responsibility for estimating it.

**The author's premise is that you sign up for the work you are going to do.  What if work is assigned to you?  Does the author's point still hold?**