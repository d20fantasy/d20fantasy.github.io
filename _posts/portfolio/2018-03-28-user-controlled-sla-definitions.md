---
layout: post
title: User-controlled SLA Definition Notifications
img: "assets/img/portfolio/SLA Definition Workflow.PNG"
tags: [ServiceNow,Enhancement,Workflow]
---

Within our instance of ServiceNow, we have more than 20 separately governed organizations with different standards and expectations for their Service Level Agreements...<!--endexcerpt-->

Any time a new help desk wanted different timings on the notifications or different recipients of the notifications, we would have to create a new SLA Definition workflow. We wanted to pass this power off to department administrators, but granting workflow_admin to users just for this purpose creates too many security risks just to provide a convenience.

My colleague, Kevin Loenker, came up with this idea for a form enhancement and I figured out the back-end adjustment to the default SLA workflow:

![Screenshot of SLA Definition Notification Section](/assets/img/portfolio/SLA Definition Notification Form.PNG)

![Custom SLA Definition Workflow]({{ page.img | relative_url }})

Users with the ability to create SLA Definitions are now able to configure notifications:

- that go out at 25%, 30%, 50%, 60%, 75%, and/or 90% of the defination duration.
- that go out at 100% and (optionally) go out again every additional 100% indefinitely
- to be sent to specific users
- to be sent to the ticket's group's manager, owner, or members
- to be sent to the ticket's assignee
- to be sent to designated groups' managers, owners, or members

They can do all of this via the SLA Definition form without ever needing to create a new workflow.