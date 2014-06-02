---
layout: post
title: "FBO Problem 4: Lame Sorting for Search Results"
date: 2014-06-02 10:45:54 +0200
comments: true
categories: [BetterFBO, FedBizOpps, FB-Oh-No, search results, sorting, keyword relevance, UX]
---
{% imgcap right /images/fbo_sorting.png 314 "Really, this is all you have for me, FedBizOpps?" "Sorting criteria in FedBizOpps" %}
Not to continue beating you over the head with it (even as I ready my club once again), but when it comes to search results presentation, little things matter a lot.  For applications backed by massive data stores, users need every bit of help we can give them to select and sift through big results listings to find what they're looking for.  Even something as seemingly inconsequential as the design of a sorting function can make a big difference for usability.

It's probably not going out on a limb when I say that most users of [FedBizOpps](https://fbo.gov/) spend a large portion of their browsing time on the search results page.  By default, the results listings are shown in reverse chronological order which would seem to have some value for regular users of the site interested in seeing what's been recently added or updated.  The user can re-sort the list according to three other attributes corresponding to columns in the table -- *Agency/Office/Location*, *Type*, and *Set-aside* -- and is able to sort in ascending or descending order.  All of what I've described might not prompt a major outcry, but as I'll explain, the fact that the feature's developers phoned it in really hurts the usability of the search results page.<!--more-->

First of all, while the selection of column attributes falls between questionable and all-right in terms of giving the user useful information to determine which listings to investigate further, they're utterly useless for sorting.  Why, you ask?  Let's take *Set-aside* as an example.  The list of set-aside values is:

* Competitive 8(a)
* Economically Disadvantaged Woman Owned Small Business
* Emerging Small Business
* HUBZone
* Partial HBCU / MI
* Partial Small Business
* Service-Disabled Veteran-Owned Small Business
* Total HBCU / MI
* Total Small Business
* Very Small Business
* Veteran-Owned Small Business
* Woman Owned Small Business

From the user's perspective, sorting on an attribute is most useful when adjacent values are similar as is the case with values that have a natural ordering or ranking.  In the case of *Set-aside* and the other non-date sortable attributes though, that's not the case.  It's just a list of names that can be sorted alphabetically, same as if it were a list of names of dentists in your area or brands of breakfast cereal.  Sure, you can place the Cheerios and Chex next to the Cocoa Puffs, but that doesn't make them like one another.  A much better option for the user in this case would be to use the search refinement form accessible via the *Search by Agency, Set-aside, State, and Type* link on the search results page to select the set-asides you're interested in as a filter.

{% img center /images/fbo_refine_search_form.png 830 FedBizOpps search refinement form %}

A more appropriate attribute for sorting might be NAICS code since they're structured in a way such that codes that are numerically near one another are related.  For example: all codes beginning with *11* are for *Agriculture, Forestry, Fishing and Hunting*, all codes starting with *21* are for *Mining*, and so on.

Secondly, the single most useful sorting criteria for most searches is just plain missing: **keyword relevance**.  If I do a search on [FBO](https://fbo.gov/) right now for *construction AND hvac*, the system returns over 250 results.  Even if I limit the search to the past 7 days, I still have almost 40 listings to comb through.  Wouldn't it be great if the system were able to **prefer results that are deemed more relevant to my keywords** - for example, ranking opportunities higher where:

* All keywords appear as a single phrase
* All keywords appear in close proximity to one another
* One or more keywords appears in the opportunity subject line

Little touches like this might take more time to program and cost a little more to deliver, but they can make a big difference in end user outcomes.

So if that's what's wrong, then how could it be done better?  I have a few humble suggestions for improvements:

* By default, order search results by keyword relevance with the relevance algorithm defined using some of the cues outlined above.
* Also allow users to sort by alternative criteria such as: posting date, number of days left to respond, etc.
* Allow the user to toggle between sorting types by clicking links or buttons rather than making a selection in a drop-down menu.
* It's fine to use table column headers as sorting links if you're using a table for displaying your search results.  If you do so, make sure it's obvious what the current ordering of results is.
* If your search results are displayed in list instead of a table, consider using links with very descriptive text like: *Prefer recently posted items* and *Prefer items relevant to my keywords*.

