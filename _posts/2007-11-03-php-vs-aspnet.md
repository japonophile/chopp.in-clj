---
layout: post
title: "PHP vs ASP.NET"
date: "2007-11-03"
type: post
published: true
status: publish
---

I just had a very interesting exchange with a friend of mine about which web technology to adopt. We were mainly comparing **[PHP](http://php.net)** and **[ASP.NET](http://asp.net)** (leaving JSP, Ruby etc aside for now).

If we were to develop a medium/large size website, which technology should we choose? The interesting thing was our different backgrounds: we both studied computer engineering and learned programming at school on Unix-like systems, but after that, my friend mainly developed on Windows using Microsoft development tools, and I continued developing in Unix (actually more Linux). While his main tool is Microsoft Visual Studio, mine would be Eclipse or even... vi(m)! We really didn't want to argue on this, so we tried to list "objective" differences and compare the pros and cons of ASP an PHP.

So we came up with general statements found randomly on the web:

- **PHP**: platform independent, open-source, fast (performance), widely used, suited for small websites, MVC not well separated except when using a good framework
- **ASP**: Microsoft, closed-source ;), maybe heavier than PHP but suited for large websites, good framework to separate view from model

At this point, none of us was able to say that one technology is "better" than the other.

Being used to open-source software and DIY solutions, I know PHP and have never touched ASP.NET. As for my friend, he thinks that having to type commands in a terminal is "pre-historic" and shouldn't be needed anymore: You should be able to create your interactive website, connect to the database etc just by a few mouse clicks. And he showed me how Microsoft Visual Studio allows this. On the other hand, PHP does not have _one_ framework like ASP.NET, it has many (I talked about Tigermouse [recently](http://blog.japonophile.com/2007/09/23/tigermouse-un-framework-pour-applications-web/), but there seem to be more mature frameworks like [Symfony](http://www.symfony-project.com/) etc). You need to choose your framework, choose your IDE also. Can Zend Studio compete with MSVS? As far as I know, PHP does not have one simple, unified development environment, which seems to be the biggest difference between ASP.NET and PHP.

I will remain a fan of PHP and open-source solutions. But this discussion with my friend made me wonder the following: When you want to quickly develop a large application with a short time-to-market, are open-source solutions performant enough? Or are they only for the people who "have time"? The following is an excerpt of the MySQL website download page:

[![MySQL Downloads]({{ site.url }}{{ site.baseurl }}/images/2007/11/mysql-downloads.thumbnail.jpg)](http://blog.japonophile.com/wp-content/uploads/2007/11/mysql-downloads.jpg)

MySQL Downloads

So to use open-source free products, I need **time + experience**, which is worth a lot of money I think.

