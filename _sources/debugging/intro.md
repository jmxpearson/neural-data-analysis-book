# Debugging

In the following chapter, we'll start to think systematically about debugging. While it's tempting to think of debugging as an occasional nuisance programmers have to face, the kind of thing we do less and less of as we write better code, the hard truth is this:

> **Everyone writes buggy code.**

The difference between novice and experienced programmers is simply that the latter _assume_ their code includes bugs and take steps to address it. In some cases, these steps are proactive, including writing [automated tests](https://en.wikipedia.org/wiki/Unit_testing) and [defensive programming](https://en.wikipedia.org/wiki/Defensive_programming). But when bugs still occur (and they always do), good programmers also know this:

> **Debugging is a _science._**

I am not exaggerating. Proper debugging requires
1. a **hypothesis:** What do you believe is going wrong with the code?
1. a **prediction:** What would happen if you changed the input data or the conditions under which the code is running?
1. a **test:** Can you change the code or its inputs (or examine something happening while the code is running) that can confirm or refute your hypothesis?

Novice programmers most often have trouble debugging because they fail to generate a hypothesis about why code is not doing what they want. And that is often a result of having an incomplete mental model of how code works. It's also the reason that, even for experienced programmers, debugging parallel or asynchronous code remains difficult: these require mental models that are challenging to grasp and reason about.

In the following exercises, we'll explore this process by working through some concrete examples.