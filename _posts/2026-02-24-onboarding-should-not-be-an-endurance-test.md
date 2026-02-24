---
layout: post
title: "Onboarding should not be an endurance test"
image: /assets/images/record-shop.jpg 
slug:  onboarding-should-not-be-an-endurance-test
date: 2026-02-24T12:33:50
categories: ["platform teams", "product thinking"]
---
One of the most exciting things is starting a new job or assignment.
One of the most frustrating things can also be starting a new job or assignment.
There is so much to learn, so many people to meet, and above all, you want to show that you are the right person for the role.
And everything that prevents you from doing the job you were hired for is distracting and often infuriating.


## Onboarding
We should not underestimate the long-term damage a bad onboarding experience can cause, nor the positive impact of a good one. 
I have experienced both.
And I know that my frustration surfaces more easily at the places where it was not good.
Even months after starting.

Telling someone “it is what it is” or “don’t worry about it” doesn’t help. It just sets the wrong tone from the start.

### Software engineer example:
Track down documentation(is there any?), configure the development environment, install tools(what is allowed?), connect to the right repositories, align with company conventions(are there even conventions?) and only then start understanding the project itself.

### Sales representative example:
Get access to the CRM, configure its settings, find email templates, find pricing sheets, discount rules, contract templates, reporting dashboards, and lead sources.

Then figure out which fields actually matter, how deals are really approved, and where the “real” numbers are tracked.

## All those before you
The situation becomes even more frustrating when you realize that everyone before you experienced the exact same problems.
They all figured it out.
Some may even have written it down.
Often that documentation is outdated, incomplete, or impossible to find.
(Sometimes it feels like companies try to fix documentation quality simply by switching to another tool. But that’s a different topic.)
The knowledge exists. 
It just isn't properly shared. 

## Inner source tool configuration

![inner source confoguration](/assets/images/tool-config.png)

A powerful solution is an inner-source configuration repository.
“Configuration as code” is already a common principle in software development so why not apply it to workplace setup as well?

> "If you can write it down, it should be scripted"

Instead of writing “how-to” wiki pages, make the setup executable.
- Every configuration becomes code.
- Every setup step becomes a command.
- Every tool installation becomes reproducible.

### Security and Ownership
- There is a single source of truth.
- From a security perspective, configurations are auditable.
- Anyone can propose improvements.
- Changes are reviewed.
- Knowledge becomes version-controlled.

### In combination with a task runner
Having scripts is a huge plus. 
Making them easily accessible makes the difference.
Depending on the user profile(s) there are some options. 
I have used both cli applications as ui apps.
The repository defines the actions and the CLI or UI simply executes them.

### As a bonus: team specific configurations
Once setup is treated as code, it becomes easy to extend it for team and product specific needs. 
A core configuration can define the company wide standards, while individual teams maintain their own layers on top. 
Tools, workflows, shortcuts, conventions. 
Everything lives in the open.
Instead of hidden tweaks and private notes, team knowledge also becomes shareable and improvable by default.

## Tool configuration as a product
Onboarding should not be an endurance test.
It shouldn’t depend on who happens to sit next to you.
If something can be written down, it can be scripted.
And if it can be scripted, it can be shared.


---
_Header image by https://www.pexels.com/nl-nl/@mickhaupt/_
