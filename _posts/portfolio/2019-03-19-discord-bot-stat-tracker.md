---
layout: post
title: Discord Bot Stat Tracker
img: "assets/img/portfolio/Discord Bot.png"
date: March, 19 2019
tags: [Integration,App,ServiceNow]
---

Using data provided by my [ServiceNow Web Scraper](/2019/03/26/servicenow-web-scraper.html) app, I created an integration with Discord, a slack-like web application that provides text, voice, and video chat servers for gaming communities.<!--endexcerpt-->

The data is parsed and creates a daily record of participants progress. Every morning, after the progress is recorded, ServiceNow contacts the Discord API and a bot informs the server of the players' progress.

![Screenshot of Discord Bot displaying video game stats]({{ page.img | relative_url }})

The admittedly "written very much for our specific use-case" code can be found my [GitHub Repository](https://github.com/earlduque/The-Division-2-Discord-Tracker), but you will at least be able to see how I did it.