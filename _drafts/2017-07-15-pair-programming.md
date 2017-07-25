---
layout: post
title:  "Pair programming - to do or not to do?"
date:   2017-07-15 00:00:00
cover:	/assets/images/pair_programming.jpg
disqus: true
---

Pair programming is the activity of two programmers cooperating to write code using a single computer. In this post I'm sharing my thoughts about the pros and cons of this approach.

The technique originates from the practices of Extreme Programming (XP) defined by Kent Beck in his book [Extreme Programming Explained](https://www.amazon.com/Extreme-Programming-Explained-Embrace-Change/dp/0321278658/ref=dp_ob_title_bk){:target="_blank"} over 15 years ago.

### The rules

Usually one developer assumes the role of "driver" and uses the keyboard to write code, just as in solo programming. The other becomes the "navigator" - observing the process and making sure the driver doesn't "drift off" and sticks to the gist of the task at hand (think: "Oh, I guess I should now refactor this method... What does it do right there? I guess we should change that too..." - the navigator is there to say: "No! Let's stick to the main task - the rest is irrelevant for now.").

These roles should be changed every now and then - some propose fixed time intervals, i.e. every 10 minutes, others, such as TDD advocates, suggest that switching should happen according to the "red-green-refactor" cycle (e.g. one person writes a failing test and the other one fixes it by writing the appropriate code).

Changing roles is important for keeping focus on the task. Our attention span is quite short and so a person staying inactive for too long could lose their focus.

<!-- But sometimes in practice it looks like: 1 dev is thinking and coding, and the other is watching him, discussing with him and giving suggestions -- after some time they switch. -->

### The setup
The ideal hardware setup for pair programming is as follows:

- a big desk - so that two people can comfortably sit at it,
- one computer,
- two keyboards and mice - it's impractical to pass them to each other when switching roles - it's better to have two sets,
- two monitors with mirrored screen - it's much easier to look right in front of you than to look to the side on a single, common monitor.

### Pros
Pair programming brings several improvements to solo programming:

<!-- - Less time wasted (e.g. social media, reddit, youtube, foosball, staring out of the window) -->
- Less time wasted - nowadays there are so many distractions that it's easy to waste your time at work. All the social media, news sites, notifications are time-eaters. When pair programming, though, you cannot make a pause and check Facebook in the middle of a task, because your partner is right next to you! This gives you a great shield against time wasters.
- Working in a pair is more motivating (you want to 'impress' the other person, or at least not look dumb, so you try to be more sharp and focused)
- When one person gets tired, the other one can pick up the pace, allowing them to rest - but in the meantime there is still progress in the task!
- "Two heads are better than one" -- mistakes are more easily spotted
- You can learn from each other - approaches to certain problems, knowledge of the language, libraries, frameworks
- Sharing the knowledge of the system at hand -- reducing the "bus factor", eliminating silos
- Overall the task can get done sometimes even quicker, and usually better
- Reduces the need for back-and-forth code reviews -- pair programming is one big code review all the time! :)
- Team spirit increases -- 'we solved it TOGETHER'

### Cons
- Very tiring -- constant focus and attention is exhaustive, a day-long PP session can make you dog tired...
- Requires patience - your colleague may type / think slower, you need to communicate etc. -- it puts your patience to a test
- Seems to be a waste of resources - but it isn't!! (especially to some managers) -- therefore might be hard to get acceptance for PP --> use the 'pros' arguments to convince them ;)
- Is less comfortable (depends on the setting), unless you have a very large desk, two big monitors, two keyboards and two mice -- but still you're using 1 PC, so eg. holding back with some action while your colleague is working is still a slight discomfort
- Requires communication -- some developers prefer to work on their own and are inherently reluctant to program in a pair -> try short sessions first? 15 minutes to 'warm them up'?
- Requires discipline - best done regularly, eg. 1 day a week, 1 day every 2 weeks -- otherwise it is easy to 'skip it', because of the aforementioned discomforts it brings
 

## Overall
Do it, everybody will benefit: the developers will learn more, the tasks will be done better and usually more quickly, knowledge will be better spread out aroung the team (no silos)


