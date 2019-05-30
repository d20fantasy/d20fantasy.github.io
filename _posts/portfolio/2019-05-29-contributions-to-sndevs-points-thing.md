---
layout: post
title: Contributions to SNDevs Points Thing
img: "assets/img/portfolio/Points Thing.PNG"
tags: [ServiceNow,Slack]
---

![Points Thing Bot in action]({{ page.img | relative_url }})

`Points Thing` is a bot on the [SNDevs](https://sndevs.com/) Slack workspace. Users in this workspace are able to offer points to users for helping answer a question, contributing to the community, or any other reason needing positive-reinforcement.<!--endexcerpt-->

The bot has had around six contributors so far and anyone is encouraged to fork [the source repo](https://github.com/ServiceNowDevProgram/sn-slack-points-thing), intall the app via studio, create a feature branch, commit a change, and then in GitHub submit a pull request to the `ServiceNowDevProgram/sn-slack-points-thing` master. 
*Collaborative projects are the best projects!* Shout out to [@j4rodm](https://twitter.com/j4rodm), [@caseybarela](https://twitter.com/caseybarela), and [@andrewjbarnes](https://twitter.com/Andrewjbarnes) for keeping the dream alive.

Here are my contributions so far:

#### Portal page for Points Leaderboard [link](https://github.com/ServiceNowDevProgram/sn-slack-points-thing/pull/1)
- Created a portal page that will display the top 20 on the points leaderboard (by default)
- Also allows the user to search for a User ID or User Name to see specific people's score if they are not in the top 20.

#### Moves the chat.postMessage REST message to a script include #2 [link](https://github.com/ServiceNowDevProgram/sn-slack-points-thing/pull/2)
- Moves the chat.postMessage REST message to a script include so that sending chats to Slack will be easier for future business rules as more features are added.

#### Logo for the slack app [link](https://github.com/ServiceNowDevProgram/sn-slack-points-thing/pull/9)

#### Point record fix [link](https://github.com/ServiceNowDevProgram/sn-slack-points-thing/pull/12)
- Fix to the business rule that would record when a point was given so that we can start gathering at least three months of data for the next update...

#### ++ Recent Points Update [link](https://github.com/ServiceNowDevProgram/sn-slack-points-thing/pull/13)
- Now that we have three months of data, Points Thing bot now says how much points the target has received in the past three months instead of total over all time. 
- It also lets them know if they are the top scorer in the past three months, they get a first place emoji, second place emoji, or third place emoji. Ranks 4 through 10 also get a star emoji.

#### Leaderboard Update [link](https://github.com/ServiceNowDevProgram/sn-slack-points-thing/pull/14)
- Updated the leaderboard page to account for the new points system. The page now shows the leaderboard for the past thirty days and the leaderboard for all time.

#### Changing of "(X total)" points in message to "(Level X)" [link](https://github.com/ServiceNowDevProgram/sn-slack-points-thing/pull/15)
- Changed the display of "total points" to tiered levels since the inclusion of total points took away the emphasis of the points over the last three months.

#### More random responses. Better Code Structure [link](https://github.com/ServiceNowDevProgram/sn-slack-points-thing/pull/16)
- Adding a few more random messages for the response.
- Changed the structure of how the random message is generated from a cumbersome switch case to a simple array of messages. This will make adding more messages in the future easier to do.