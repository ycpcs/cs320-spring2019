---
layout: default
title: "Lecture 18: Static Analysis"
---

# Static Analysis Tools

A static analyzer inspects the program's code (source code or possibly object code) in order to look for bugs in the program.  You can think of this as being like an automatic code inspection.

Advantages

-  Fast
-  Automatic

Software can adopt a brute-force checking approach: for example, testing very large numbers of paths through the program that would be hard to do through testing and code inspection.

Disadvantages

-  Nontrivial program properties are undecidable, meaning that a static analyzer cannot be completely precise in its determination of possible program behaviors.  This means that the static analyzer must estimate possible program behaviors.

If the static analysis approximates in the direction of consistently overestimating possible program behaviors, then it may produce some false warnings: program executions that would be a bug, but which can't actually happen in practice.  However, the static analysis warnings are guaranteed to not miss any bugs (of whatever particular kind of bug the analyzer is looking for).

If the static analysis approximates in the direction of consistently underestimating possible program behaviors, then it may miss some real bugs.  However, it will never produce any false warnings.

If the static analysis does not approximate consistently in either direction, than both false warnings and missed bugs are possible.

In some ways, it would seem like overestimating is always the best alternative.  However, if the static analyzer produces 100,000 false warnings for every real bug it finds, then it will take too much time to sort the real problems from all of the noise.

Consistenly underestimating would also seem to be nice, because we're guaranteed not to have to look at any false warnings.  However, if the static analyzer misses too many real bugs (and possibly doesn't find any bugs at all), then it's not useful.

FindBugs
--------

In practice, it is possible to engineer a static analyzer to make tradeoffs between overestimating and underestimating by trying to focus on likely program behaviors.  One way that static analyzers can do this is by making use of common idioms appearing in code.  Programmers tend to solve similar problems in similar ways.  This means that both correct code and incorrect code will tend to follow common patterns.  These patterns can be recognized by the static analyzer to help find bugs, and also to help weed out false warnings.

[FindBugs](http://findbugs.sourceforge.net/) is a static analysis tool which focuses on finding bugs which result from common programming mistakes.

[Examples of bugs found by the FindBugs static analysis tool.]

### Using static analysis effectively

Not every warning issued by a static analysis tool is necessarily interesting.

Some kinds of warnings are not relevant (e.g., malicious code vulnerabilities in an app not exposed to malicious code)

False warnings - the warning is inaccurate, and doesn't identify a real defect

Any false warnings in unchanging parts of the codebase will be reported over and over again as the static analyzer is used on the system

Harmless bugs - the warning is accurate, but the consequences aren't harmful

Same issue as false warnings - once reported, they will be reported over and over again

To use static analysis effectively in the development process, we need a way of calling attention to the most interesting warnings, while excluding the uninteresting ones.

A good approach is to keep a history of all static analysis warnings reported on the system over time.  Each time the static analysis is run, it is compared to the history.  All of the static analysis warnings in the latest report which were also reported in earlier reports are filtered out, leaving developers to audit only the newest warnings.
