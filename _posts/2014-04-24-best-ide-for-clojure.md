---
layout: post
title: "(best? ide-for-clojure)"
date: "2014-04-24"
type: post
published: true
status: publish
---

Hello, Clojureverse!

Since I started learning [Clojure](http://clojure.org/), I tried different development environments, including Eclipse and LightTable, but today, I am back to the simplest-thing-that-could-possibly-work: VIM.

[![Eclipse with CCW]({{ site.url }}{{ site.baseurl }}/images/2014/04/Screen-Shot-2014-04-24-at-11.58.44-PM-300x185.png)]({{ site.url }}{{ site.baseurl }}/images/2014/03/Screen-Shot-2014-04-24-at-11.58.44-PM-e1398351633900.png)I started with **[Eclipse](http://www.eclipse.org/)** with [counterclockwise](https://code.google.com/p/counterclockwise/). It has syntax highlighting and a REPL and it was OK when I worked on my first Clojure project: clogo, a LOGO turtle interpreter. (I'll surely come back on this one). It certainly does the job, but I would not really recommend Eclipse for Clojure... too heavyweight.

After installing **[Leinigen](http://leiningen.org/)** and using VIM for a short period of time, I stumbled onto **[LightTable](http://www.lighttable.com/)**, which is clean and nice, with a minimalistic design. It seemed promising as it includes a REPL with real-time evaluation of the Clojure code you type. But I found it not very practical, because unlike an autocompletion feature, I like my REPL to wait until I'm done typing. So I ended up copying and pasting code from LT to my REPL, which I thought was probably not the best way. (The other thing that I didn't like about LT is that the screen could only be split vertically; maybe it's improved today).

In quest of a more integrated environment, I went back to **[VIM](http://www.vim.org/)** and tried the **[NailGun server](http://www.martiansoftware.com/nailgun/background.html)** for REPL integration. It is OK, and although the execution of Clojure code in a separate window seemed a good idea, it looks like NG is sometimes getting lost when I inadvertently close it's buffer. That's really a pain.

[![MacVim and vim-fireplace]({{ site.url }}{{ site.baseurl }}/images/2014/04/Screen-Shot-2014-04-24-at-11.58.37-PM-300x187.png)]({{ site.url }}{{ site.baseurl }}/images/2014/03/Screen-Shot-2014-04-24-at-11.58.37-PM-e1398351671714.png)At this point, I found **[vim-fireplace](https://github.com/tpope/vim-fireplace)** (earlier called foreplay.vim) which is simple and really nice. It will find your REPL and automatically connect to it, and it can not only execute a block of code in a single keystroke, but also run your tests, or let you see the documentation for any function.

So to summarise: my environment today is Leiningen, and MacVim with vim-fireplace (+ vim-clojure-static and rainbow\_parentheses.vim plugins). I am using clojure.test for testing, and cloverage to measure my test coverage. And I use criterium library together with VisualVM when I have to look at performance.

Voilà. Enough talking. Let's start coding...
