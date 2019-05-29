---
layout: post
title: Timed Approval Reminders
img: "assets/img/portfolio/Timed Approval Reminders.PNG"
tags: [ServiceNow,Workflow]
---

![Screenshot of Workflow]({{ page.img | relative_url }})

Users that relied on emails often reported to us that they would forget about approvals pending their review.

To solve this, I created a simple workflow that would trigger reminder notifications after 1 day, 3 days, 7 days, and every 7 days after that until the approval request was acted upon or no longer needed.<!--endexcerpt-->

Approval time-to-completion improved immediately!

If you are wondering what stops the infinite loop on the bottom branch of the screenshot, remember that any activity that triggers the "end" activity cancels all other active activities in the workflow.