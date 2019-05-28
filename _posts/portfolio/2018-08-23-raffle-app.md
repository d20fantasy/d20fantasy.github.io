---
layout: post
title: Raffle App
img: "assets/img/portfolio/raffle.png"
date: August, 23 2018
tags: [App,ServiceNow]
---

![image]({{ page.img | relative_url }})

For the 2018 UC Tech conference, there was a need for a raffle application<!--endexcerpt--> that would:

* Draw a winner from a list of entries
* Allow individual entries to be added to the pool
* Allow multiple entries to be added en masse
* Allow multiple winners to be drawn
	* While allowing the option of the previous winner to be either included or excluded from subsequent drawings
* Allow confirmation of the winner being present, otherwise re-draw
* Allow the reseting of the results
* Allow the resetting of all entries
* Allow for private drawings vs. public drawings
* Be recorded in a database
* Be reportable
* Be accessible without creating an account
* Be entirely mobile friendly

And just so happened that no such thing existed for our immediate use. I was presented the problem and within a day I had a working concept and within another day we had the full application up and running and being used live at the conference.

A month later we wrapped it up nicely and released it for use by anyone at our university.

The application is open-sourced and can be found at [earlduque/ServiceNow-Raffle](https://github.com/earlduque/ServiceNow-Raffle) on GitHub.