---
layout: post
title: Create Dev Update Set from Story
img: "assets/img/portfolio/Create Dev Update Set.gif"
tags: [ServiceNow,QoL]
---

![Demonstration of Related Link that creates URL for another instance]({{ page.img | relative_url }})

The hot thing to do nowadays is to create update set managers. Before we get there though, I made a simple utility that would allow story assignees to select a `Create Dev Update Set` related link that would push a URL to the user's clipboard<!--endexcerpt-->:

`https://DEV_INSTANCE.service-now.com/nav_to.do?uri=sys_update_set.do%3Fsys_id%3D-1%26sysparm_query=name=GROUP-STORY_NUMBER-SHORT_DESCRIPTION`

Which would load the user into the Developer instance with the update set name already configured according to our internal naming standards of `Group name - Story Number - Story Short Description`

Simple but effective!
