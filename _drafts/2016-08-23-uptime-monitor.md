---
layout: post
title:  "Monitor your local services with Uptime"
date:   2016-08-23 00:00:00
disqus: true
---

I have recently come across the need to monitor a few services at work. Because they are only
available in the local network and not in the wide-open Internet, all of the SaaS solutions
were out of the question.  

So I was looking for a simple, locally hosted application to monitor my services. All I needed was to 
check if the services were up or down by issuing an HTTP GET request.  

My first steps were directed at Nagios and Zabbix, two names I had previously heard from some Ops guys
at my previous job. But boy... they are so complicated! After glancing at the installation instructions
I quickly abandoned both and kept on looking for something simpler.  

After futile Google searches I turned to GitHub as my last resort (I was on the verge of writing the 
monitoring application myself). And then I stumbled upon project [Uptime](https://github.com/fzaninotto/uptime).  

It turned out to be pretty easy to install, configure and test, and after several minutes I was convinced that
this application exactly fulfilled my needs. Even the fact that the project is no longer actively maintained
didn't change my mind.

In this post I will demonstrate how to use Uptime to monitor a website that uses basic authentication.

### 1. Install dependencies
The project uses node.js and MongoDB, so we will first need to install those. Below are instructions for Ubuntu:

```
sudo apt-get install -y nodejs
sudo apt-get install -y nodejs-legacy
sudo apt-get install -y npm
sudo apt-get install -y mongodb
```

TODO:

robomongo  
create db --> uptime  
create user --> zarówno w bazie 'admin', jak i w bazie 'uptime'

basic auth: https://groups.google.com/forum/#!topic/node-uptime/tLxc6OGyYi8

