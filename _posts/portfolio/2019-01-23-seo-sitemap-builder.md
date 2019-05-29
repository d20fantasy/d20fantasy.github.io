---
layout: post
title: SEO Automatic Sitemap generator
img: "assets/img/portfolio/SEO Result.png"
tags: [ServiceNow,App,Scripted REST API,SEO]
---

![Example output of automatically generated sitemap]({{ page.img | relative_url }})

In an effort to optimize our Service Portal for SEO (Search Engine Optimization) I created a page via the Scripted REST API that would automatically generate an XML sitemap for ingestion by search engine bots like Google and Bing. <!--endexcerpt-->

You can see an example result in the above screenshot; Navigating to `https://INSTANCE.service-now.com/api/uocd2/seo` triggers a script that builds an entire sitemap of all available public Service Portal pages, including every knowledge base category, knowledge base article, and service catalog category/details page. Since it is generated at the time of the request, the sitemap is always up-to-date for the search engine.

In the first four months of the implementation, our production instance's sitemap has been crawled over 1000 times.

Additionally, I implemented a user-agent grabber so that we can see how often the sitemap is grabbed and by whom:

![Screenshot showing the tracking of several bots that have crawled our sitemap](/assets/img/portfolio/SEO Tracking.png)