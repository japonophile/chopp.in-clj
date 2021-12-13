---
layout: post
title: "Software Testing: Dogmatic or Pragmatic?"
date: "2008-03-01"
type: post
published: true
status: publish
---

As a software engineer, and particularly in the medical field, software testing is a subject I find very important, so I'd like share with you some thoughts about it.

I watched on InfoQ a [debate about TDD](http://www.infoq.com/interviews/coplien-martin-tdd) which took place at [JAOO '07](http://jaoo.dk/aarhus2007/conference/) with Jim Coplien and Bob Martin. Martin started the debate by declaring: "**it is irresponsible for a developer to ship a line of code he has not executed in a unit test.**"

First thought: of course! We, software engineers, learn by experience that code which has not been executed (tested) cannot be considered working (understand: should be considered not working). So yes, Martin is right. We tend to like clear and straight statements, because they are easy to understand and agree with: yes, every line of code should be executed in a unit test. But when you think of it, there are several problems with this:

- Is it because a line has been executed in unit test that it is properly tested? Read: 100% code coverage in terms of executed line of code is not that meaningful in itself: I can write 100% coverage tests and still ship buggy code.
- (Assuming you write meaningful tests:) What is the cost of writing unit tests to achieve this 100% coverage? And is the cost justifiable, does it really add value for the customer?

Recently, I also read this article on Javalobby: [Practical Unit Testing](http://java.dzone.com/news/practical-unit-testing). And I liked it, because it is more balanced and reflected than the single statement of Martin.

In fact (and this is the tricky problem in software testing): the most **meaningful test** is the most difficult to write. To take a practical example: in my organization, (a year or two ago) we've been an using automated test tool called Agitator (by [Agitar Software](http://www.agitar.com/); note that it is now part of a tool called AgitarOne). This tool basically automatically generates tests based on Java code and allows you to "agitate" your code, that is, run methods with all sorts of arguments, to try finding bugs. The problem is if you agitate your code "randomly", at best, you find trivial bugs such as lack of null-checking etc. On the other hand, if you want to use the tool in a meaningful way, you need to spend a lot of time creating mock classes and test datasets, to introduce domain knowledge in your tests (which the tool does not have). Whether you do it using using a tool such as Agitator, a xUnit framework, or manually, this effort is not going to change a lot. (I'm not saying you should not use a tool, but don't think using a tool will substantially reduce the effort of writing meaningful tests).

The goal of software testing is simple to understand: ship bug free code. But it is extremely difficult to achieve due to the gigantic size of the search space. And it is therefore difficult to give good advices on how to do that in practice. In my opinion, we ought to be very careful with dogmatic statements, and always ask ourselves how to **increase test efficiency** (increase pay-off for the effort spent in writing tests), rather than increase test coverage.
