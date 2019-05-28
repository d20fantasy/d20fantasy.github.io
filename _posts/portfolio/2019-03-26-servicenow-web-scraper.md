---
layout: post
title: ServiceNow Web Scraper
img: "assets/img/portfolio/Web Scraper After.png"
date: March, 26 2019
tags: [App,ServiceNow]
---

While searching for an online resource that would visit specified websites to gather information and return it back to a central location for later use, the best resources were often not cheap or didn't have all the functionality I needed <!--endexcerpt--> (primarily the ability to then package the data in a REST retrievable JSON object).

Additionally, any application that claimed to be able to do in ServiceNow was also hidden behind a pay-for product. So I ventured off to create my own:

![Screenshot of Web Scraper app in ServiceNow](/assets/img/portfolio/Web Scraper Before.png)

In this ServiceNow application, you can designate several endpoints (web pages) in a task record, and upon insertion, ServiceNow will go to the web pages, grab the source code of the website and return it back to the application record.

Optionally, you could also elect for ServiceNow to remove HTML tags from the result (to make it look cleaner) or specifically look for JSON objects (helpful if your target web page is already constructed via JSON objects, making the result even eaiser to parse through).

The results are then placed into a prepared JSON object that can be used elsewhere in ServiceNow via a simple GlideRecord and JSON.parse() of the result field.

![Screenshot of Web Scraper JSON Object result]({{ page.img | relative_url }})

The code is stored in a private GitHub repo, keeping this one in my pocket for now!