---
layout: post
title: Cross Instance User Management
img: "assets/img/portfolio/Cross Instance User Management.PNG"
tags: [ServiceNow,Scripted REST Api]
---

Whenever a new user wants to be added to our instance of ServiceNow, their manager submits a ServiceNow request to the Service Management team and the new user is first added to a "learning" instance to be trained. To speed up the time-to-completion of adding the user to the separate instance, I automated it via the Scripted REST API.<!--endexcerpt-->

The Service Management Office can initiate the user-management process from the production instance, which means the technician doesn't have to ever log into the learning instance nor do we need to grant extra user-admin roles to those technicians.

The technician is even provided context to the success of the automation:

![Alt Text]({{ page.img | relative_url }})

- If the user doesn't exist in the target instance yet
- If the user was created successfully
- If the user already is a member of the group that grants the necessary roles
- If the user has been succesffuly added to that group