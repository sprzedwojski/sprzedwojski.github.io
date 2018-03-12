---
layout: post
title:  "IntelliJ IDEA: multiple configurations at once"
date:   2018-03-12 00:00:00
cover:	/assets/images/cogs.jpg
disqus: true
---

I've just recently come across a problem where I wanted to run 2 configurations in IntelliJ IDEA with a single keystroke.

The matter at hand was that I had a Spring Boot application with a React frontend, created using `create-react-app`.
The Spring Boot was handled by Gradle and React with Webpack and Node.

Both the backend and the frontend were able to reload themselves upon changes in code and I didn't want to forgo that during development by building the frontend and then serving it from the backend controller. Therefore I wanted to run them independently.

Both were in the same project so I created a configuration in IDEA for each of them. The problem was: I had to manually run each configuration to get the application app and running!

That being extremely inefficient I started searching for a way to run them "together".

Unfortunately a quick Google search revealed that IDEA does not support such behaviour out-of-the-box. You _can_ define a "Before launch" action, but that would not work here, as neither of the configuration terminates! They both **run** for as long as you want the application to run.

Fortunately, I found [this StackOverflow answer](https://stackoverflow.com/a/20857719/1972469) mentioning an IDEA plugin called [Multirun](http://plugins.jetbrains.com/plugin/7248-multirun).

Sure enough, the plugin works perfectly! You can set the order of configurations and even introduce delays between them.   
Now a single Shift + F10 does the trick ;)

![Multirun configuration](/assets/images/multirun.png)