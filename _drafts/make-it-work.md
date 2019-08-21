---
layout: post
title:  "Make it Work, Make it Right, Make it Fast"
categories: programming
---

Probably my favorite development saying and design principle.

{% include post-styling.md %}

![make it work](/assets/img/posts/makeit/whiteboardwords.jpg){: .image-sized .center-image } 


1. Make it work.
1. Make it right.
1. Make it fast.

(and also "I are engineer", a saying from a professor I had.)

## 1. Make it Work

This is usually the prototyping or alpha stage. We are trying concepts and making this fun and playable. It's usually rough but it's suppose to be a proof of concept

## 2. Make it Right

Usually, getting it working requires some quick hacks and not well architected, unless you really know what you're doing. This is making it so the parts of the software are not spaghetti code and actually implements the behavior and not just fakes it. An example of where this will be required is the new tree chopping and rock hitting. It fakes the server side checks and limits on the number of resources available so you can get unlimited wood right now. Making it right would mean I need to finish the implantation and make it so the trees have a set number of wood you can collect from them, controlled by the server side.

## 3. Make it Fast

The most important part. Once it works right, it still may not be fast. This is where we return back to hacks to speed up things. Making things right in general should make every thing run better but the goal there is to make it easier to update,maintain, and add more later
Sometimes there's speed issues and it's only after cleaning up the implementation can they be found and properly dealt with. Pre-mature optimization is bad because it can lead to a lot of wasted work, make it harder to add things later, and can be fixing a symptom, not a cause of an issue
As for optimizing a game, a lot of things are implemented at first in a naive way. That's part of the make it work step. After a bit of testing and implementing other related systems, we can take a step back and see there are better ways to do it. That is part of the optimizing part. Making it right and making it fast. There's a lot of design patterns and principles to help improve code quality but sometimes you have to get it working first