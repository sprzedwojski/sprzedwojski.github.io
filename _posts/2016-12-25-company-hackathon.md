---
layout: post
title:  "How we held a company hackathon that was awesome"
date:   2016-12-25 00:00:00
cover:	/assets/images/hackathon_main.jpg
disqus: true
permalink: /2016/12/25/company-hackathon.html
---

Recently we organized a company hackathon at my workplace. Being one of the organizers and a participant I wanted to share my experiences.

### Our Goals

We had been tinkering with the idea of an internal coding event for quite some time. The main goals that we wanted to achieve were the following:

1. Have fun
2. Learn new technologies
3. Build team spirit and collaboration
4. Create something durable and useful

#### 1. Have fun

This point is quite obvious. As the hackathon was organized in the employees' free time, we wanted to make sure that the activity would be fun and rewarding. Nobody wants to sacrifice their personal time to do some tedious and boring coding tasks.

#### 2. Learn new technologies

In our day jobs we tend to work with the same tech over and over - tech which can also be quite dated. Some of us are more fortunate and get to experiment, but most are not that lucky. With the hackathon we wanted to provide the participants with the opportunity to play with the most cutting-edge technologies to sharpen up their skills.

Although it is possible to experiment with new tools on your own, it certainly is more entertaining to do so with others.

#### 3. Build team spirit and collaboration

Given that in our day jobs we tend to work with the same people all the time, we wanted to group participants randomly so they have a chance to work in other configurations. The benefits included learning to cooperate with other people as well as tightening bonds between employees who do not collaborate regularly.

Additionally, contrary to a typical hackathon where teams compete for the best solution, we wanted to enforce collaboration by making each team build a diffrent component of the final solution. Only all the parts working together would guarantee the success of the hackathon's creation.

#### 4. Create something durable and useful

We wanted to avoid a situation where the projects created during the hackathon would be dumped right after it's finished. Therefore we decided to build a tool that would benefit us in our daily lives at the company.

We struggled with the topic for a bit, but at some point during a conversation over coffee an idea was born. Our company is situated in a big house and there is one toilet on each of the four floors. It often happens that one has to run up and down the stairs to find a toilet that is available.

As engineers we approached the problem pragmatically: let's build a tool to monitor the availability of toilets! We would do that by placing a light sensor in each of the toilets (most of them don't have windows). As ridiculous as it sounds the idea quickly gained traction and suddenly everybody was on board with it.

### Execution

We had some fundamental ideas about the hackathon's organization:

- Make it during the day - too many hackathons are held at nights or as 24h events, thus disturbing our natural daily rhythm.
- Make it short - we wanted to limit the time to 6 hours to incentivize simple solutions and prevent over-engineering.
- Group everybody together - to avoid sitting at our regular desks and feeling like it was just another day at work we hung out in the chillout room instead with everybody sitting in sofas or poufs with laptops in their laps coding in a casual atmosphere.

Below is the diagram of the solution we set out to build:

![Hackathon project diagram](/assets/images/hackathon_scheme.png)

There were 3 tasks:

- Connect a light sensor to a Raspberry Pi, detect light level in a toilet and post the availability status to a server.
- Create a server application that will collect data from Raspberries, expose a web gui and a REST endpoint.
- Create a Slack bot that will respond with toilet statuses.

I will not get into technical details, but the Raspberry Pi was programmed in Python, the web server app was made with Java 8 in Spring Boot and the Slack bot uses JavaScript running in Node.js.

Moreover, to expose the participants to the cloud, the server app and the bot were deployed in Heroku using an automated build from GitHub.

### Conclusion

All in all the hackathon was a great success - we achieved the desired functionality, had lots of fun and gained at least a glimpse into some of the most current technologies on the market. In fact our GitHub repositories are still being committed to even after the event with further upgrades to the components of the system. Even people who did not attend the hackathon are participating!

If you've never organized such an event in your company I totally recommend it. It will bring your developers together and help them remember that programming is fun!

[//]: # (photo: https://www.pexels.com/photo/coffee-writing-computer-blogging-34676/)
