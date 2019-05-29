---
layout: post
title: YNAB ServiceNow Integration
img: "assets/img/portfolio/YNAB ServiceNow Integration.png"
tags: [ServiceNow,YNAB,Integration]
---

![YNAB Logo overlaid ServiceNow Integration App]({{ page.img | relative_url }})

One of the earliest full integrations I ever did. This app integrates ServiceNow with YNAB (You Need a Budget), a really great budgeting app.<!--endexcerpt-->

This ServiceNow App contacts the YNAB API, retrieves your available budgets, their categories and subcategories, and their budgeted, activity, and balance amounts.

I included a ["Getting Started"](/ynabnow.html) help page in this app too to walk the user through configuration.

YNAB natively doesn't automatically export data, so this app is useful if you want to do things like:

- Reporting via ServiceNow
- Sending notifications to anyone when certain numbers hit a threshold
- Displaying certain numbers on portal widgets
- Sending the information to other integrations like Slack

The application is open-sourced and can be found at [earlduque/ynab-now](https://github.com/earlduque/ynab-now) on GitHub.