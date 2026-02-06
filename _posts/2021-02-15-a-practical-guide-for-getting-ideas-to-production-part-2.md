---
layout: post
title: "A practical guide for getting ideas to production - Part 2"
image: /assets/images/header-2.jpg
slug: a-practical-guide-for-getting-ideas-to-production-part-2
date: 2021-02-15T20:25:33
categories: product ownership
---
[Part 1]({% post_url 2021-01-25-a-practical-guide-for-getting-ideas-to-production-part-1 %}) of this series was about how to get an idea worked out into artefacts. In this post I will illustrate this flow a bit more with examples. In that post I stated that **'Writing user stories is literally the least of your concerns'** because if you have a structured flow in which you describe artefacts properly the stories will come almost automatically as we can see in this post. [Part 3]({% post_url 2021-02-24-a-practical-guide-for-getting-ideas-to-production-part-3 %}) will be about translating these artefacts to the user stories and acceptance criteria.

## **The reason**

Imagine that we work for a retail webshop that sells clothing. We are always looking for ways to increase our sales since that is often the whole idea of any shop. We think that we should introduce some features which will engage our existing customers more. 

When thinking about the reason for features it is important to be honest. We like to 'make the world a better place' and 'add value to our customers' but in this case I think the main focus is revenue. Of course I want the customer to have a smooth user experience, and that will improve my changes on reaching my business goals, but I think I in this case should write the goal from a business perspective:

## **Epic Goal**

We think that implementing a way to create and redeem coupon codes (What)

Will give an incentive to buy more often at our shop (Why)

To our new and existing users (Who)

We know we have succeeded when:

*   75% of all sent coupon codes are actually used in transactions
*   13% higher sales by customers who received a coupon vs customer who haven't
*   5% increase of recurring customer sales

## **User flows**

I can think of a couple of features for this epic:

*   Creating and managing codes
*   Coupon code statuses (sent, redeemed, invalid…)
*   Tracking the customer-coupons combinations
*   Sending coupon codes
*   Redeeming coupon codes

For this example we will use the customer's user flow. This person received a coupon code somehow and wants to redeem it during a transaction.

With the user flow we describe the simplest path (happy path) and what I call extensions (edge case) to this path. You can already recognize subjects that are related to testing. 

So while making the flow I came both to understand some certainties now have some questions that I need to get answered:

*   The cart button is only active when there are items added (is this already implemented?)
*   We need a coupon validation
*   Coupon codes has dates and statuses (I need to put this in the data model)
*   Prices need to be recalculated in the page
*   Hmm, can you actually redeem multiple codes in one go? 
*   Could people have more than one code and would they want to try them to see what the result will be?

![](/assets/images/User-flow.jpg)

This is pretty cool. I think that in this phase these kinds of questions should be raised and answered as much as possible. Often they result in great new and extra features. Also thinking about these things now will result in less discussions and unclarity in sessions with teams in later stages.  

## **UX**

Since we now have a global understanding of the functionality and the flow we can start thinking about the best experience for the user. It often goes both ways: you make a UX based on a flow but learn a better and smarter way to solve the problem. This will often result in adjustments in the flow. Often even for the goals. This is also perfectly fine in this phase: you are creating something and that means a lot of learning and revisioning.

While making the UX I found some new questions and considerations:

*   Is there a way to store discounts already?
*   We need to adjust the invoice so we can print the coupon discount on it?

Well, no problem. There are just a couple notes or questions I will have to take in account.

## **UI**

We take the UX and apply the appropriate styling to it. We can also create a working click model to try it out and export the html/css if needed.

![](/assets/images/UX.jpg)

## **Data model**

We now have the flow our users will follow and we have designed how this will work and what it will look like. Now we just have to think about data: What fields will it contain? Does it have dependencies to other things? What changes in other entities will be needed? We call this the logical data model. Creating and/or understanding the logical data will improve your understanding of the application and the logic behind it.

![](/assets/images/Data-model.jpg)

It's also a good practice to see if we can get the data we need to validate our epic goals: 

*   75% of all sent coupon codes are actually used in transactions
*   13% higher sales by customers who received a coupon vs customer who haven't
*   5% increase of recurring customer sales

If not we might change the data model so we can track our progress towards reaching the epic goals.

## **And now we write stories**!

I think we are pretty complete for now. There will always be some things you forgot or new questions but that is just part of software product development. These things are often an addition or small change to the artefacts we just created.

If you take a look at the user flow you will see that the first stories are easily to be found there. The same goes for the acceptance criteria. When looking at the UX we can find some additions and looking at the UI design we can complete these. In part three of this series we will write the out a bit.
