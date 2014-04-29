---
layout: post
title: "FBO Problem 2: Page Links Disrupt Workflow"
date: 2014-04-29 09:05:14 +0200
comments: true
categories: [BetterFBO, FedBizOpps, FB-Oh-No, search, search results, paging, pagination, UX]
---
[FedBizOpps](https://www.fbo.gov) proudly and prominently displays the number of active opportunities listed on its homepage above the search form.

{% img center /images/fbo_active_opportunities.png Active federal opportunities %}

At the time of this writing, there are **26,411 listings that were posted within the past 90 days**.  (Broadening the search to include opps from the past 365 days, which is the highest value allowed by the search form, it shows that there are *40,127 results*.  Anyone able to shed some light on exactly what constitutes "active" in the comments?)

Let's suppose I attempt a search on a broad keyword like "construction". I get search results numbering well into the thousands.  In this case, [FBO](https://www.fbo.gov) does what a lot of sites do: it lets me page browse through the results page by page while giving me some control over the number of items per page and parameters used to sort the results.<!--more-->

{% img center /images/fbo_search_results_form.png FBO search form %}

We've all become so accustomed to this user interface paradigm over the years that some of the absurdity might be lost on us.  Like what rationale drove the decision to provide links for the first seven pages?  Or what would prompt someone to click through to page 5, and why would we not be equally likely to want to go to page 95?  And while we're still in the box: why shouldn't we be allowed to view results ten at a time if we wish?

On the modern web, displaying long lists of items is often best and most efficiently handled by automating requests for more items.  Referred to by web heads as "infinite scroll", this describes an approach where the application senses that the user is nearing or has reached the end of the list and responds by automatically loading and displaying more results at the end of the list.  It's a technique that's become common over the past several years, especially for social media applications that display a timeline or a stream of content like [Pinterest](https://www.pinterest.com/), [Twitter](https://twitter.com/), [Facebook](https://www.facebook.com/).

Using infinite scroll offers a number of advantages over more traditional pagination links like those used by [FBO](https://www.fbo.gov).

* The user no longer is no longer forced out of the natural flow of scanning and scrolling to load another page of results.  When combined with well-designed sorting and filtering functions, the browsing experience for most users is made dramatically more efficient through the addition of infinite scrolling.
* As a design decision, automatic scrolling simplifies the experience for users of mobile devices and tablets.
* Removing the page links and the results-per-page dropdown menu removes clutter and/or frees up screen real estate for other purposes.

Infinite scroll isn't perfect for every kind of application, and a quick scan of the Internet will show you that plenty of smart companies still make heavy use of it.  For example, [Amazon](http://www.amazon.com/) uses pagination because online shopping is one of the few verticals where research shows that it's actually more effective and provides users with a better experience, and [Google](https://www.google.com/) uses it because, frankly, if they're not able to show you what you want within the first five search results, they won't be in business for long.  It should be made clear though that these are very specific cases backed by research and testing, and more often than not, pagination links are used by developers as a default option for long lists rather than as a conscious decision made with the best interests of the user in mind.

All of that said, there are certain guidelines that should be followed when implementing infinite scroll in an application, and they can be summed up in one sentence: **the user should always feel in control of the page**.  In practice, this means that parts of the page that aren't specifically intended to be dynamic should be stable, and the results list itself should be under the user's control.

* The total number of items in the list - search results, in this case - should be clearly visible when the list is initially loaded.
* The application should deliver visible feedback to the user when new results are being loaded.  In a perfect world, the feedback would include information about the current position in the overall list - e.g. "Loading results 21-40 of 68".
* The application should provide easy options for jumping to the top or bottom of the list.
* Common site elements such as navigation should be visible or at least reachable regardless of current position in the list.
* [Don't break the browser.](/blog/2014/fbo-problem-1-dont-break-the-browser/)  Ideally, clicking the back button and forward again should reload the list in its previous state with respect to position and loaded results.

Pagination will be around for years to come, but you won't find it anywhere on [BetterFBO](http://betterfbo.com/).  The search results listings will be engineered around a **page-free viewing experience** that simplifies browsing for the user and **optimizes for viewing on mobile devices and tablets**.
