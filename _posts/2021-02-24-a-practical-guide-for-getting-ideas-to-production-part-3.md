---
layout: post
title: "A practical guide for getting ideas to production - Part 3"
image: /assets/images/part3-header.jpg
slug: a-practical-guide-for-getting-ideas-to-production-part-3
date: 2021-02-24T19:11:04
categories: ["product ownership"]
---
[Part]({% post_url 2021-01-25-a-practical-guide-for-getting-ideas-to-production-part-1 %}) [1]({% post_url 2021-01-25-a-practical-guide-for-getting-ideas-to-production-part-1 %}) of this series was about how to get an idea worked out into artefacts. In [part 2]({% post_url 2021-02-15-a-practical-guide-for-getting-ideas-to-production-part-2 %}) I illustrated this flow a bit more with examples and created the artefacts. This part will be about translating these artefacts into user stories and acceptance criteria.

![](/assets/images/header-2.jpg)

The result of our activities in part 1 and 2 are the following artefacts:

*   Epic goal
*   User flows
*   UI and UX designs
*   Data model

# **Epic Goal**

We think that implementing a way to create and redeem coupon codes (What)

Will give an incentive to buy more often at our shop (Why)

To our new and existing users (Who)

We know we have succeeded when:

*   75% of all sent coupon codes are actually used in transactions
*   13% higher sales by customers who received a coupon vs customer who haven't
*   5% increase of recurring customer sale

# **User flows**

For this example we took the customer's user flow. This person received a coupon code somehow and wants to redeem it during a transaction. 

![](/assets/images/user-story.jpg)

_As a customer of the webshop,_

_I want to be able to redeem coupon codes,_

_So that I receive discounts._

# Acceptance criteria

When looking at the user flow I can easily spot the user input actions and the actions made by the system and I can describe both their behaviour in the form of acceptance tests. 

![](/assets/images/attd-user-stories.jpg)

## Happy path

First I describe the happy path:

**Scenario:** Redeem coupon code

_Given I have items in my shopping card_

_And I have an order with the value of € 134,-_ 

_And coupon code 2345EX is a code for 30% discount_

_When I fill in 2345EX in the coupon field_

_Then the system shows me the code is valid_

_When I click on the Apply button_

_Then the total price in my cart is updated to € 93.80_

_And I see a discount displayed of € 40.20_ 

_When I click on the Checkout button_

_Then I see the Checkout screen_

As you can imagine this is a small part of the total end to end tests but it covers our new addition to the product.

## Unhappy path

I also see my first deviation from the happy path: an invalid coupon code. I write another scenario.

**Scenario:** Try an invalid coupon code

_Given I have items in my shopping card_

_And I have an order with the value of € 134,-_ 

_And coupon code 2345EX is a code for 30% discount_

_When I fill in INVALID-CODE in the coupon field_

_Then the system shows me the code is invalid_

_And the Apply button is disabled_

_When I fill in 2345EX in the coupon field_

_Then the system shows me the code is valid_

_And the Apply button is enabled_

_When I click on the Apply button_

_Then the total price in my cart is updated to € 93.80_

_And I see a discount displayed of € 40.20_ 

_When I click on the Checkout button_

_Then I see the Checkout screen_

## Edge cases

I also see an edge case that would be worthwhile to describe: what happens when we go back from the updated prices to the first screen and do everything over again? My experience tells me to expect the unexpected always.

# **UX/UI**

I will make sure now that I update my UI right away. I did not include the following in my original design:

*   The system shows me the code is valid
*   The system shows me the code is invalid
*   The Apply button is enabled
*   The Apply button is disabled

In this case they are not quite revolutionary designs but I decide to show them anyway because I am rather safe than sorry:

![](/assets/images/ui-user-story.jpg)

# **Validate**

We defined successfactors while describing the epic goal. We often tend to forget about them but we have to consider them with each story. We said that we know we have succeeded when:

*   75% of all sent coupon codes are actually used in transactions
*   13% higher sales by customers who received a coupon vs customer who haven't
*   5% increase of recurring customer sale

We have thought about the connection Customer - Coupon code - Order in the data model and coupon codes have a status. 

For this story I would add a task that we change the status for the personal coupon code to 'Redeemed' after checkout. For a non-personal I would like to increase the redeemed coupon count with 1. We now can be sure we can find all the success factors in our database and we can see if we are reaching our goal. 

![](/assets/images/pexels-lukas-590045.jpg)

Lukas - Pexels.com

# **And now we are done!**

Our first story is done. We have many more to write. In part 2 we found some more that are related to this one. We can now present it to the team and discuss possibilities and ways to implement. I am pretty confident that I thought of many things. I am also pretty sure that I might have missed things and that changes might be needed. And that is perfectly okay! That is an important part of Product Ownership.
