---
layout: post
title:  "Pair programming - to do or not to do?"
date:   2017-07-27 00:00:00
cover:	/assets/images/pair_programming.jpg
disqus: true
---

Pair programming is the activity of two developers cooperating to write code using a single computer. In this post I will share my thoughts about the pros and cons of this approach.

The technique originates from the practices of Extreme Programming (XP) defined by Kent Beck in his book [Extreme Programming Explained](https://www.amazon.com/Extreme-Programming-Explained-Embrace-Change/dp/0321278658/ref=dp_ob_title_bk){:target="_blank"} over 15 years ago.

### The rules

Usually one developer assumes the role of "driver" and uses the keyboard to write code, just as in solo programming. The other becomes the "navigator" - observing the process and making sure the driver doesn't "drift off" and sticks to the gist of the task at hand.

If you're developers you must know this feeling when you've spent an hour implementing a certain solution, only to find out five minutes later that it should have been done completely differently. When we're in the "flow" state it's easy to get lost on the technical details forgetting about the business context. The navigator is there to look at the "bigger picture", making sure the driver doesn't get lost on particularities of a certain implementation when they shouldn't be doing it that way at all.  

These roles should be changed every now and then - some propose fixed time intervals, i.e. every 10 minutes, others, such as TDD advocates, suggest that switching should happen according to the "red-green-refactor" cycle (e.g. one person writes a failing test and the other one fixes it by writing the appropriate code). 

Changing roles is important for staying focused on the task. Our attention span is quite short and a person being "hands-off" as the navigator for too long could lose their focus. On the other hand it is also beneficial for the driver who gets to rest.

### The setup
The ideal hardware setup for pair programming is as follows:

- a big desk - so that two people can comfortably sit at it,
- one computer,
- two keyboards and mice - it's impractical to pass them to each other when switching roles - it's better to have two sets,
- two monitors with mirrored screens - it's much easier to look right in front of you than to look to the side on a single, common monitor.

### Pros
Pair programming brings several improvements to solo programming:

- Less time wasted - nowadays there are so many distractions that it's easy to waste your time at work. All the social media, news sites, notifications from various apps - these are time-eaters. When pair programming, though, you cannot make a pause and check Facebook in the middle of a task, because your partner is right next to you! This gives you a great shield against time-wasters.
- Working in a pair is more motivating - you want to 'impress' the other person, or at least not look dumb, so you try hard to be sharp and focused.
- Constant progress - when one person gets tired, the other one can pick up the pace, allowing them to rest - all while making progress in the task!
- Instant code review - you can catch a lot of potential bugs or eliminate mistakes because the code is being constantly reviewed by the navigator. It also reduces the need for back-and-forth code reviews afterwards.
- Learning skills - especially if the pair consists of a junior and a senior developer, this is one of the best ways for the junior to learn. They have an experienced programmer at their side, whom they can observe, ask questions and get instant feedback from.
- Knowledge sharing - if features are developed in a pair, the knowledge of the system is better "spread out" within the team, meaning it is less likely there will be "silos" of knowledge, where a lot of information is in the hands of one person only ([bus factor](https://en.wikipedia.org/wiki/Bus_factor){:target="_blank"} = 1). It is also a great way to introduce a new team member to the project.
- The task gets done better, and sometimes even quicker - because of the lack of time-wasters and constant focus on the task.
- Raises team spirit - you get the feeling of 'we solved it TOGETHER' :)

### Cons
Wow, all this sounds great, but... where's the catch?  
Below are the downsides of pair programming:

- Very, very tiring - constant focus and the need to communicate are exhausting, making pair programming suitable only for rather short periods of time. As a rule of thumb I would say 3-4 hours maximum, and not every day.
- Requires patience - your colleague may type or think slower, sometimes you may need to explain them something - it puts your patience to a test.
- Seems to be a waste of resources (especially to some managers) - but it isn't! Because of that it might be hard to get acceptance for pair programming from the management - but you can always use the 'pros' arguments to convince them ;)
- Is less comfortable (depends on the setting) - unless you have a very large desk, two big monitors, two keyboards and two mice - but still you're using one PC, so eg. holding back with some action while your colleague is working is still a slight discomfort.
- Requires communication - some developers prefer to work on their own and are inherently reluctant to cooperate. It might be hard to convince them to 'open up'.
- Requires discipline - it is best done regularly and in a scheduled manner, eg. 1 day a week, 1 day every 2 weeks - otherwise it is easy to 'skip it', because of the aforementioned discomforts that it brings.
 

## Overall
Despite the disadvantages I strongly recommend you try pair programming at work. From my experience everybody will benefit: the developers will learn more, the tasks will be done better and usually more quickly, knowledge will get spread out among team members, the code will be of a better quality and your team spirit will go up.

Just remember to practice it with caution: regularly, but not too often and not for too long at a time.

How about you - do you have any opinions on pair programming? Let me know in the comments!