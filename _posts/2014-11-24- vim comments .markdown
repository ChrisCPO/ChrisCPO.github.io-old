---
layout: post
title: "Vim Comments"
date:   2014-11-03 20:05:00
categories: jekyll update
tags: featured
image:
---

topics :vim, :comment

Something totally awesome I just learned in vim is how to comment out a line and even a block, this seems like something a lot of vim users don't know how to do. I was trying to remap the caps lock key so I don’t end up just ripping it off of my keyboard in some sort of wookie rage. In vim if you hit :map it lists a bunch of key maps, :map! will list other ones as well. However in that first list I noticed a bunch of commands that are called “TComment”, I started playing with them and below are the commands that comment out ruby and I would assume rails files as well;

vim comment commands 

block comment 
enter visual mode    “shift” + “ v”
highlight block with movement keys 
to comment hit “g” then “>”
to uncomment hit “g” then “<”

single line 
enter visual mode “v”
then hit “g” then “c” 
uncomment the line the same way

Comments are great for debugging and problem solving but your code should speak for itself, so remember to delete them before you submit that pull request. 

Now back to that pesky caps lock key...
