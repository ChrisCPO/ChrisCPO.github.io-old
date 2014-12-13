---
layout: post
title: "Vim Comments"
date:   2014-11-24 12:00:00
categories: jekyll update
tags: Regular
image:
---

* topics :vim, :comment

Something totally awesome I just learned in vim is how to comment out a line and even a block, this seems like something a lot of vim users don't know how to do. I was trying to remap the caps lock key so I don’t end up just ripping it off of my keyboard in some sort of wookie rage. In vim if you hit ":map" it lists a bunch of key commands, ":map!" will list other ones as well. However in that first list I noticed a bunch of commands that are called “TComment”, I started playing with them and below are the commands that comment out ruby and I would assume rails files as well; 

**block comment**

* enter visual mode    “shift” + “ v”
* highlight block with movement keys 
* to comment hit “g” then ">"
* to uncomment hit “g” then “<"

note - One cool trick is to do this without hitting the "g" key which then just shifts the lines in the dirrection of the "</>" keys. This is very helpful for those html.erb files which dont like to respond to the "=" key well. 

**single line**

* enter visual mode “v"
* then hit “g” then “c” 
* uncomment the line the same way

note - This seams to only work if your cursor is above certian words or if it is at the beginning of the line over nothing, I have found my self using the block comment method for single lines more.

Comments are great for debugging and problem solving but your code should speak for itself, so remember to delete them before you submit that pull request. 

Now back to thAT PESKY CAPS LOCK KEY...
