---
layout: page
title: "YNAB Now - Getting Started"
permalink: /ynabnow.html
hide: true
tags: [YNAB,ServiceNow,Integration]
---

# Getting Started

This page assumes you have already installed the integration! If you haven't yet, install this [GitHub repo](https://github.com/earlduque/ynab-now) via studio.

## Get your access token

This integration only works with personal access tokens right now. To get your access token, follow the instructions [here](https://api.youneedabudget.com/#personal-access-tokens).

Once you get your token, go back to ServiceNow and navigate to `YNAB Now` > `Properties` and paste the token into the `Personal Access Token from YNAB Developer Settings` system property and click `Save` (Make sure you didn't accidentally and leading or trailing spaces/white-text in your token value).

## Retrieve your budgets

Navigate to `YNAB Now` > `YNAB Now Budgets` and click the `Retrieve Budgets` button and wait about 10 seconds. You can also check the progress of the REST communication by navigating to `YNAB Now REST Calls` and seeing if the call you just initiated has received a response yet.

Refresh the Budgets list and you should see all the available budgets you can import. Open the record of the one you want to use.

## Retrieve your budget's categories

Once the record for your selected budget has loaded, click the "Update Categories" button and wait about 10 seconds.

Navigate to `YNAB Now` > `YNAB Now Categories` to see the cumulative budget, activity, and balances for your budgets!

Alternatively, you can also navigate to `YNAB Now` > `YNAB Now Category Groups` to see your top-tier categories and each record will have a related list of individual categories within it.

## Use-cases

- Reporting
- Sending notifications to anyone when certain numbers hit a threshold
- Displaying certain numbers on portal widgets
- Sending the information to other integrations like Slack