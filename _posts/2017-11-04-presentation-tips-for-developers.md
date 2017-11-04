---
layout: post
title:  "Presentation tips for developers"
date:   2017-11-04 00:00:00
cover:	/assets/images/conference.jpg
disqus: true
---

Recently I've had the chance to watch many technical presentations as well as give a few of them myself. These experiences have led me to some conclusions regarding giving tech talks and I wanted to share my observations.

I will not discuss the general rules of presenting. Instead, I will focus on aspects that are key to programming or technical presentations.

### Keep the terminal up
Very often when several commands have already been executed, the terminal prompt ends up at the bottom of the screen, which makes it difficult for the audience to see. Either you as the presenter are blocking its view, or it simply is too low for people in the farther rows to see.

Therefore make sure to press that "Enter" a few times after each command to push it up. Or simply configure your terminal not to take up the whole height of the screen, but, for example, the upper half only.

### Make the code big and visible
The code in your IDE or text editor open with your normal, everyday configuration will likely be too small for the audience. The same applies to the terminal window. 

Make sure to increase your font size or even enter a "presentation mode", which some IDE's natively have (e.g. IntelliJ IDEA).

You can also ask your audience if the code is big enough to be seen comfortably from the last rows. Make sure you know the shortcut keys for increasing and decreasing font size in your editor to be able to quickly adjust it.

If you present code in slides, just make sure the font is big enough, as it would be inconvenient to change it during the talk.

The color scheme of your editor is also important. If you are in a dark room, a dark color scheme will do, but it will be less readable if there is sunlight coming through windows or when the lights are on. Therefore it is usually safer to go will light color schemes.

### Let the code unfold
It is common to simply copy-paste the code from the editor to your slides. However, such a block of code can be difficult for the audience to grasp all at once and can leave them overwhelmed. They will usually either read the code and not follow you, or they will not have understood the code.

I learned that it is much better to show code in small increments and let it "unfold", as if you were writing it on the go. It is much easier to understand code this way.

You can present it in consequent slides, adding new lines of code to each of them. Alternatively, if you are showing it from an IDE, you can set up git aliases to move between commits (as described [here](https://blog.jayway.com/2015/03/30/using-git-commits-to-drive-a-live-coding-session/){:target="_blank"}).

Of course the best way is usually to...

### Prefer live coding to already prepared code
If you feel confident in your skills I recommend doing a live coding session rather than presenting already prepared code.

This way it is much more engaging for the audience, as they can see the code as it is being created. It is also the easiest for them to follow and understand.

Of course for it to be effective you need to practice a lot beforehand, be able to type quickly and know your editor / IDE well (e.g. shortcuts). It would be very boring to watch you search for some option in the menu with a mouse ;)

To minimize any potential risks (i.e. code is not compiling due to a silly mistake which you are now unable to trace because of the stress of being in front of 200 people... you get my point) make sure to combine this method with setting up git aliaseses and having your code ready just in case.
This way if something goes wrong you can just skip to the nearest commit and continue from there.

### Prepare and test
If you are showing the code, always make sure it compiles and produces the desired output. Don't make the changes directly in the slides - always copy and paste from an IDE. It would look very unprofessional if someone spotted a compile-time error in your code during the talk.

If you are doing live coding, prepare yourself well. Write all the code from scratch at least twice, ideally more. Try to hardwire it into your "muscle memory" - there will be a lot of stress during the presentation so being able to code "without thinking" is very helpful.

Make sure to test your prepared commits - does switching between them work as expected? Is their order correct? Does every commit produce a working example?

### Do not assume your audience knows what you're talking about
In every presentation on any topic your audience will certainly contain people who have no knowledge in that field. It is always a good idea to sacrifice a small part of the presentation to present the basics of the topic, even if you are going to talk about advanced concepts.

For example, if I were to speak about advanced features of React, Redux etc., I would always begin with a slide or two about what React is, what are its basic principles and why people use it.
It will take 2 minutes but this way you make sure everybody in the room can follow your talk (even if they don't uderstand everything that comes next).

### Conclusions
Tech talks are usually all about the code - so make it a centerpiece! Make it big, let it unfold and seduce your audience :)

And don't let any pesky errors ruin your talk - so prepare yourself and your code beforehand.

I hope my small tips will help you deliver even more awesome presentations!