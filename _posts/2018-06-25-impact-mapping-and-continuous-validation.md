---
layout: post
title: "Impact mapping and continuous validation"
image: /assets/images/0-3.jpg
slug: impact-mapping-and-continuous-validation
date: 2018-06-25T22:38:31
categories: ["product ownership"]
---
There is always a reason for making software. Let’s rephrase that: there _should_ always be a reason, at least from a business perspective. How else could our products have any impact?

Whether we want to make an app that that seamlessly connects riders to drivers or build a community where you can hire and rent apartments while earning tons of money: it is basically all about adding value and solving problems from a software point of view.

### **Impact Mapping**

Impact mapping is a technique that can be helpful in defining the impact you want your product to have with all that follows. _Why are we doing this?_ You first define the desired impact with some criteria that you consider necessary to make this impact. These criteria stand for the _how_ and the _what_.

The example below from by impactmapping.com illustrates how impact mapping works:

![](https://media.licdn.com/dms/image/C4D12AQGRQ99XBFuSJA/article-inline_image-shrink_1500_2232/0?e=2129500800&v=beta&t=PSaeKMAHur1TWLiWysnPHP8Yfcea4HSNpE2VPV5gLb8)

_foto: www.impactmapping.org_

*   We want to reach 1 million players on our platform.
*   We think that there are three personas that can help us with that: players, internal employees and advertisers.
*   We think we know how they can help us with that
*   We think we know what will facilitate them on our platform.

### **Assumptions**

With impact mapping we make a lot of assumptions. In the example below we assume that the actor called Player can help us in making the desired impact (1 million users). We also assume that Player will do this by inviting friends, and we make the assumption that semi-automatic invites will help.

### **Following up on your stories**

The thing I don’t see happening often is following up on the impact of a piece of functionality. We have a review or demo and sometimes we get feedback from users. Yet apart from some performance monitoring we do not really know a lot about the impact we are making. Did we make valid assumptions?

### **Continuous validation**

With continuous validation we also make many assumptions. In contrast to automatic unit tests we want to keep validating the same assumptions in production as long as the functionality is alive, and not run it only once. It is very common that the impact of one feature is diminished by a newer one. To create great projects this is something you really want to know and should act on.

We introduce validation as an extra dimension to a user story. We call this an experiment. These experiments will run scheduled in production as long as the functionality is there. The experiment for the example above could be:

**Experiment:** By giving players the option to invite friends semi-automatically the number of players will increase.

**Baseline:** Get the current number of players.  
**Assume:** There will be a 10% increase in new players.  
**Time:** 1 month.  
**Success:** Send cake to the whole team with congratulations.  
**Failure:** Push message to Product Owner.

Other things I would like to know and want to create experiments for is how much the invite option is being used, who uses it, and what the assumed effect is after 6 months?

### **Impact mapping and continuous validation**

In a sense continuous validation is the automation of impact mapping. Where impact mapping is a great way to define products, continuous validation makes sure your assumptions are being validated. Not once, but as long as the functionality is alive.

Creating great products is not only about adding new cool features. It is also about removing or changing existing features whose goals aren’t met. We know which impact we want to have. Are we in any way achieving this goal? Are our assumptions right? Is there functionality that is not contributing to our goal?

Manual monitoring of all the assumptions that were made is undoable most of the times. Working software must be delivered at an ever faster pace. That’s why after continuous integration there is continuous validation.

Impact mapping:

[www.Impactmapping.org](http://www.impactmapping.org/)

