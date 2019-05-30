---
layout: post
title: Scrum Task Automation Workflow
img: "assets/img/portfolio/Scrum Task Workflow.PNG"
tags: [ServiceNow,Workflow,QoL]
---

![Scrum Task Automation Workflow]({{ page.img | relative_url }})

After heavy out-of-box usage of Agile Development in ServiceNow, we noticed that stories would have unnecessary admiinstrative overhead between the end of one scrum task and the start of the next one. To solve this, we added an optional way of handling scrum tasks via an automated workflow.<!--endexcerpt-->

![Scrum Task Automation Form Section](/assets/img/portfolio/Scrum Task Form.PNG)

Story creators are now able to designate up to five expected scrum tasks. Once triggered, the workflow automatically creates the designated scrum tasks:

- In order (when one completes, the next one automatically is created)
- With relevant information:
	- Description
	- Type
	- Acceptance criteria if a coding task
	- Testing Script if a testing task
	- Description and criteria if an analysis or documentation task.
	- Assignment Group
	- Assigned to (optional)

Additionally, the workflow can be stopped manually and it automatically stops if a testing task is marked as failed.

The ability to template our scrum tasks is especially useful as our story process always includes specific steps for testing and quality assurance. And now, when one task concludes, the next responsible person/group is immediately notified, reducing the time-to-story-completion.

## Developer Tip

The reason why the workflow runs a script to create the scrum task is because of how workflow contexts handle the `Create Task` activity when the workflow context is restarted or when the current workflow context is cancelled and a new context is started: Repeated "Create Tasks" even in new contexts will simply re-target the previously created task, instead of making a new one.

Our intent was to always keep historical record of all scrum tasks, regardless of if they failed or were cancelled. Creating the scrum task via a `Run Script` activity ensures that the generated task is always a new record. After all, the person who performs this round of scrum tasks might be different than the previous round, but we didn't want the last round to lose credit of their task completions.