---
layout: post
title: "A practical guide for getting ideas to production - Part 1"
image: /assets/images/idea-phase.png
slug: a-practical-guide-for-getting-ideas-to-production-part-1
date: 2021-01-25T18:58:56
categories: ["product ownership"]
---
In a previous blog post [The Perfect Product Owners Flow]({% post_url 2018-07-12-the-perfect-product-owners-flow %}) I explained something that I would call a typical product flow. In this flow you start with strategic goals and transform them in a controlled way to working software that your users can use:

![](/assets/images/PO-flow-final.png)

In this blog series I elaborate more on this flow in a practical way. I will share the way I often set up this product flow and what tools and methods I use for it to succeed:

![](/assets/images/idea-phase.png)

The idea phase

_It all begins with an idea or a frustration. There is either a problem you would like to see solved or there is a feature of which you are sure it will add something good for someone, somewhere, somehow._ 

## **Plan**

![](/assets/images/roadmap.jpg)

Once an idea seems to be something that could be worthwhile to investigate it should be planned. Decide when users should be able to use it. I know that your last idea often seems your best. Often a new idea gives a great deal of energy but be honest: how important is it against the rest of the ideas? The existing planning. And when the time is there you should start investigating. Just in time. But for now we will just place it somewhere on the roadmap.

A roadmap sounds very enterpicy sometimes. Something that very important people manage but an ordinary roadmap is just a dynamically ordered list of ideas with a global desired planning.

## **Design the idea**

So the day has finally come! Based on the roadmap it is time to get started on this new idea. It is time to make the idea more specific and measurable. We need to specify the desired effect we want after implementing it and we need to find out for who and what the needs of these persons are.

There are many tools to facilitate in this process but I have two main to-go-to tools in this phase:

### Product vision board

![](/assets/images/product-vision.png)

I use the product vision board for the somehow bigger ideas. A new module or a whole new product for instance. I like it because it is simple and contains everything I need in this phase.

A product vision describes, visualises, and validates your product or concept vision and strategy. It captures the target group, user needs, key product features, and business goals.

### Epic goals

For the smaller items I use something called an epic goal. I often use this for additions to the products that are also planned on the roadmap and follow the same flow. An Epic goal contains the following:

**We think that by implementing** <_capability/feature/option_\>

**We will solve/Will give the opportunity** <_problem_\>/<_new possibility_\>

**For** <_persona_\>

**We know we have succeeded when** <_measurement_\>

### Validate

The success criteria  of both the Product vision as the epic goal should be measurable as much as possible. When can we say for sure that the idea was a really good idea? Which change in behaviour, increase or decrease of usage, conversions do we want to achieve with this idea? And then, often the hardest, part of this phase comes up: what measurable values will determine if we are successful?

## **Create**

_So if, after creating a product vision or an epic goal, the idea still seems a good one to build it is time to start creating artefacts. Unleash the creator in you. For me this is the fun part. I get to think of users and how I think they will use this brand new functionality, I can think of ways to amaze them and prevent them from getting stuck or annoyed, I get to draw and sketch and think of the data they will produce._ 

![](/assets/images/design-startupstockphotos.jpg)

It is often stated that as a PO you do not have to create all artefacts by yourself but that being sad, I would really emphasise that the more you can do or understand the better your story to the team and your stakeholders will be. Please don't be frightened by something that looks technical at first like the user flows or data models below. Because they are to a certain point not technical at all. 

The artefacts I usually create are:

*   Personas
*   User flows
*   UX
*   Data model

### Personas

Personas are descriptions of the fictional characters that represent your different user types. They will help you understand who you are creating these ideas for and how this person will interact with your product.

While designing the personas they often give me great insights in what their needs are. The way an application is designed differs a great deal whether it is for a warehouse worker that needs to quickly add data, an elderly person who is looking for a product or a tech savvy person who wants to sell their product online via their mobile.

It also happens frequently that I find out a persona and even new ideas while writing the persona I thought would be the main ones.

### User flows

![](/assets/images/user-flow.png)

User flows, UX flows, or flowcharts are diagrams that represent the paths users take when using your product. The user flow shows the user's paths through the product from the start to the end.

I use the user flows for finding out and understanding the numerous interactions and flows the user will have and I am already able to foresee and prevent some undesirable paths (which will help me a great deal when I start writing the acceptance criteria). Here I can already start creating the simplest possible solutions from the end users perspective. 

While making user flows you will already see some distinction in subjects and flow that will later on represent in the backlog in the form of epics and stories and last but certainly not least in how to test the product.

### User Experience

![](/assets/images/ux-picjumbo.jpg)

![Image from picjumbo.com](blob:https://nielstalens.nl/5e44070a-d5ee-40fc-ba48-e903f2c50092)

A next logical step for me after the personas and user flows is to think of ways the general UX should be. UX design is the process of designing products that are useful, easy to use, and delightful to interact with. And since UX and UI design both are specific crafts which should be done by professionals I try to sketch just enough to get my points across.

### Datamodel

I do not expect every PO to create or change physical data models but I think the effect a new feature has on the data model is certainly something to at least realise. Often a new feature means new tables fields in the database and these fields often relate to fields in other tables. It affects your product. One very important aspect in keeping applications simple and flexible lies in proper data modelling so it could be a good investment to gain some knowledge about the subject as a PO. It often gives me great insights in how the product is structured and it makes me spot similarities in new and existing features quite easily.

### **Writing user stories is literally the least of your concerns**

I cannot emphasise this enough. Most people like to 'get cracking' from the start which means writing user stories in Jira or whatever tool as a starting point. Do not worry about user stories! If you have a structured flow in which you describe artefacts properly the stories will come almost automatically and you can be sure they will be the right thing to build for your users. 

## **Next steps**

Since we now have gathered and designed all information we need it is a good time to start creating the epics and from there on the user stories. Here I also use some criteria and ways to describe things. I write about these next steps in [part 2]({% post_url 2021-02-15-a-practical-guide-for-getting-ideas-to-production-part-2 %}).
