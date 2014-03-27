---
layout: post
title: "FB-Oh-No #1: Don't Break the Browser"
date: 2014-03-27 13:47:46 +0100
comments: true
categories: [BetterFBO, FedBizOpps, FB-Oh-No, back button, browser, tabs]
---
{% img right /images/fbo_search_results.png 500 FedBizOpps.com search results %}

Searching [FedBizOpps](https://www.fbo.gov) for new opportunities is probably the most common use case for visitors of the site.  Performing a basic search would likely include:

1. Request a search based on criteria entered into the search form.
2. Scan the list of results looking for relevant items.
3. Review the detail page for the first interesting result.
4. Return to the search results listing.
5. Wash, rinse, and repeat from step #2.

Unfortunately, the application has been implemented in a way that complicates this most common of use cases.<!--more-->

## Problem #1: Broken Back Button ##

If I attempt to use my web browser's back button to navigate from the opportunity detail page to the search results listing, the application fails to display anything and instead I see a page like the one below.

{% img center /images/ie_webpage_expired.png 600 FedBizOpps.com opportunity detail %}

Don't break the back button - it's one of the cardinal rules of web application design, but it's one that's often ignored by large, complex websites.  This is probably a minor annoyance to most users, but it's just one symptom of the development team's decision not to embed search criteria directly in the request link.  That leads to other problems that include the inability to **bookmark searches** or to **copy and paste a search link from the browser's address bar** into an email to share with a friend or co-worker as well as **adding difficulty for search engines to index the site**.

## Problem #2: No Support for Multiple Windows ##

Most modern web browsers will allow you to right-click on a link and ask to open it in a new tab (or window), so instead of clicking through to one opportunity, I might attempt to right-click and open a number of opportunity detail pages in their own tabs and review them in bulk.  This seems to work just fine, but if I then return to the search form and try to change some of the parameters - agency, NAICS code, notice type, or even just the ordering of results - the application is unable to service the request and instead displays the last opportunity detail page I opened.

So what happened?  [FBO](https://www.fbo.gov) stores information about the last page you visited on its servers and uses it when deciding how to handle your next request.  So even though you requested a change from the search form, the last request made was for the oportunity detail page, and reordering or reselecting search results from there would be nonsense, so it does the only think that it can reasonably do and redisplays the same page.

## Lesson: Follow The Principle of Least Surprise #

Most seasoned users of the application will modify their searching workflow to use the "Return to Opportunities List" button provided on the opportunity detail page, but minor inconveniences in the user experience like these indicate a deeper problem.  Good software always goes the extra mile to match the expectations and experience of its users.  Whenever it fails to do so, whatever the reasons and justifications might be, it shifts responsibility for understanding how the system works from the developer to the user.  This is always a bad tradeoff, and it's been recognized as such since well before [FedBizOpps](https://www.fbo.com) was built.

The behaviors described in this post might seem like minor annoyances or just "how the system works", but in fact they show a disregard for the traditions of the web as well as a lack of respect for you and your time.

