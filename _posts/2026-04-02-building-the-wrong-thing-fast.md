---
layout: post
title: "Building the wrong thing fast"
image: /assets/images/keep-driving.jpeg 
slug: building-the-wrong-thing-fast
date: 2026-04-02T12:33:50
categories: ["product ownership", "product thinking"]
---
If there is one thing we consistently don’t do in product development, it is providing the right context at the right moment.

We refuse to translate strategy into actual business goals.
We refuse to write proper product descriptions.
We refuse to define clear acceptance criteria.
And we definitely don’t maintain documentation.

We focus on output. Like we always have.
Output was never the problem.
Understanding what to build and why is.

## something new
Building something new has always required context. From strategy to execution.
AI does not change that.

If anything, it makes it more obvious.
AI does not know what matters. It does not know what problems are worth solving or who you are building for.

We still need to provide that context.
That is the same context we were already skipping.

The difference is that now we can build faster and seemingly cheaper.
So crap in crap out enters an new phase.
More crap faster.

## Something used
I often hear that legacy can be rebuild in a fraction of the time with AI.
The reality is that using AI to rebuild existing products will get you 90% of functionality.
But that last 10% is where all the context lives.

Legacy systems are full of decisions made for a reason.
Sometimes technical limitations.
Sometimes business rules.
Sometimes painful lessons.

If you don’t understand why something is programmed a weird non clean code, you might remove it.
And when you remove it, things break in ways you didn't expect since you have not enough context.

## Create context
We don’t need more process.
We just need context in the right places.

### Why we are building this
This is the foundation. 
And this is where things usually go wrong.

What problem are we solving?
For who?
Why does it matter?
And what will it cost?

This is:
- strategy
- business cases
- product vision
- user feedback
- market insights.
But also clear problem statements, success criteria, and trade-offs.
If this is vague, everything below becomes guesswork.

### What are we building
This is where we go from the why to scope.
This includes:

- Product/feature descriptions
- Scope boundaries
- Acceptance criteria
- Edge cases and assumptions
- Examples of expected behaviour
- Non-functional requirements

This layer prevents teams from building something that works but not the right thing.

### How it works now
Most teams underestimate this but to build or rebuild anything we need:
- user flows
- architectural decisions
- data flows
- integrations
But also the messy parts. The quirks. The constraints.
All of it!

This is where the real context of a system lives.
Especially in legacy.

### How we build it
This is where we often assume context exists but it's often fragmented.
Coding conventions and patterns, architecture principles, test strategy and such.

A lot of the most important context never makes it into documentation.
It lives in commit messages and code review discussions.

## Build a context system
Context should live close to the product.
In markdown. In version control.
Either in the product repository or in a dedicated context repository.

For items like commit messages and pull request discussions a simple action that exports these as text to the repo is quite simple.

Just start with what you can get.
Make sure it is correct and useful.
Quality over quantity.
And along the way you might find more.
Context is not static but evolves with the product.

It might even slow down development a bit.
Or make the agent ask more clarification questions.
That is good. That is how you stop building the wrong thing faster.

## Fattier, better or both
We can now build faster than ever.
Which is a very cool thing.
The real question is:
Do we finally take the time to understand what we are building?
Embed this in our ways of working?
Or do we just produce more, faster, with less people?
