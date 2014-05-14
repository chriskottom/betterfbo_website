---
layout: post
title: "FBO Problem 3: No Keyword Context in Search"
date: 2014-04-30 09:05:14 +0200
comments: true
categories: [18F, BetterFBO, FedBizOpps, FB-Oh-No, GSA, search results, keywords, context]
---
In the previous installment, we already looked at how [FedBizOpps](https://www.fbo.gov) might be improved by [displaying long lists of search results using continuous scrolling](/blog/2014/fbo-problem-2-page-links-disrupt-workflow/).  This post takes a closer look at one improvement that might be made to the structure of the results themeselves.

Imagine for a moment that you're a general contractor with a proven track record building professional-grade data center facilities, and you're looking for federal opportunities that would match your skills and experience opportunities involving *data centers* and *construction*.  So you enter those terms into the search field, and the system responds with the following results.

{% img center /images/fbo_search_results2.png 700 FedBizOpps results for data centers AND construction %}<!--more-->

The immediate and obvious difficulty with the way the search results are presented is that nowhere in the listing does the system give any indication about the **context** in which the search keywords might have been used. So while I can see from the classification codes that the first three opportunities (red/pink boxes) might relate to construction and building in some way whereas the next two (blue/aqua boxes) probably do not, the only way I'm going to know for sure is by clicking through to the listing which breaks your flow of scanning the opportunities list.  In most applications it might be possible to right click on the subject links and load the opportunity detail pages for interesting items in separate windows, we're already discussed the ways that [FedBizOpps breaks the browser](/blog/2014/fbo-problem-1-dont-break-the-browser/) when it comes to working in multiple windows or tabs.

## A Better Solution from the New Kids on the Block ##

For those who haven't been paying attention, there have been some recent developments over at the [GSA](http://gsa.gov/) as they've assembled a new team of developers, designers, and data scientists with a mandate to raise the bar for digital services delivery by federal agencies.  Dubbed [18F](https://18f.gsa.gov/), they've created quite a stir among open government nerds with their initial project - a prototype application called [FBOpen](https://fbopen.gsa.gov/) which offers a different view on the same data set used by [FBO](https://www.fbo.gov).  While the interface is a lot less cluttered, downright sparse, I like what they've done with the individual search results - being more selective about the data shown and **providing a short fragment of text from the opportunity description that shows my search keywords in context**.  It's a brilliant piece of work, even if only considered in the contrast it offers from the standard [FedBizOpps](https://www.fbo.gov/) interface and how quickly they've been able to put it out into the world.

{% img center /images/fbopen_search_results.png 700 FBOpen search results for vehicle maintenance %}

The application is intended more as a demonstration of the [web service](http://docs.fbopen.apiary.io/) they've built for searching federal business opportunity data, and so it has some basic limits that reduce its utility for opportunity search and business development activities.  Even so, it's still a very promising development and one that [BetterFBO](http://betterfbo.com) will be using as a yardstick during development and initial launch.

**Note:** Jason Hull calls out this issue along with other problems affecting the [FedBizOpps](https://www.fbo.gov) search function in a 2012 post [The Failure Of Search At FedBizOpps](http://www.opensourceconnections.com/2012/03/06/the-failure-of-search-at-fedbizopps/).  It's a thoughtful listing of some of the same flaws that [BetterFBO](http://betterfbo.com/) will be looking to remedy when it launches.