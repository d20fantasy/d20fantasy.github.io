---
layout: post
title: Random User Agent
img: "assets/img/portfolio/Random User Agent.gif"
tags: [ServiceNow,App]
---

![Examples of random user agents]({{ page.img | relative_url }})

Simple utility that will generate a random user-agent descriptor that can be used in REST call headers.<!--endexcerpt-->

	new RandomUserAgent().get("desktop")
	new RandomUserAgent().get("mobile")
	new RandomUserAgent().get("other")
	new RandomUserAgent().get()
	
Any of these commands will return user-agent strings. For example:

	Mozilla/5.0 (Windows NT 6.3; WOW64; rv:43.0) Gecko/20100101 Firefox/43.0 Seamonkey/2.40
	Mozilla/5.0 (iPhone; CPU iPhone OS 9_3_4 like Mac OS X) AppleWebKit/601.1.46 (KHTML, like Gecko) Version/9.0 Mobile/13G35 Safari/601.1
	Opera/9.10 (Nintendo Wii; U; ; 1621; en)
	
Attribution: the data for agents was provided by [phelma's repo](https://github.com/phelma/random-user-agent)

This just wraps it up into a ServiceNow utility/app. You can get the repo from [earlduque/ServiceNow-Random-User-Agent](https://github.com/earlduque/ServiceNow-Random-User-Agent), just install it in studio.