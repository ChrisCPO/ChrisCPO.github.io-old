---
layout: post
title: "EDD to TDD"
date:   2015-01-19  12:00:00
categories: TDD
tags: Regular
image:
---

* topics :TDD

A few people have asked me what EDD is, EDD is Error Driven Development and its what I learned at Metis’s Ruby On Rails development camp among many other things such as but not limited to Rails, Ruby, some Javascript, Vim, PostGreSQL while building some awesome applications using best industry practices like DRY, Cohesion and the Sandy Metz’s rules. However, there was just not enough time for us to learn TDD(Test Driven development), so we learned EDD instead. Recently I had the chance to co-work out of the Thoughtbot office where I  pair programed with my old instructors and learn some TDD in Rspec, immediately I saw a relationship between EDD and TDD.

In EDD you write code so it raises an error, write that link that you want to go to, or call a new class that you have not made yet, it requires an idea of want to do. Then you simply fix the error, refactor and repeat  till you have your desired functionality. TDD works in a similar way, though more complicated but rewarding. So the big picture for testing is to write tests, that test features and units of your code, that way if anything breaks you know about it. When you want to add new functionality to you code you write a new test for it, run the test and it will fail! Now we want to write the basic amount of code to make it pass. Once the test passes, refactor the code to achieve the desired functionality. If the test fails repeat the process. Sounds kinda familiar right? This whole process is called Red, Green, Refactor.

![screenshot](/assets/article_images/RGR.jpg)


