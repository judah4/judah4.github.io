---
layout: post
title:  "Make it Work, Make it Right, Make it Fast"
date:   2019-08-22 15:35:00 -0700
categories: programming
---
My favorite development saying and design principle.

{% include post-styling.md %}

![make it work](/assets/img/posts/makeit/whiteboardwords.jpg){: .image-sized .center-image } 

<!--more-->

1. Make it work.
1. Make it right.
1. Make it fast.

###### (and also "I are engineer", a saying from a professor I had.)  



Apparently it's attributed to Kent Beck? I don't know were I found it, but it covers how I create my software and games. 
I'm writing this in reference to my video game work, so it's going to reference fun and play. 


## 1. Make it Work

This is usually the prototyping or alpha stage. I try concepts and making this fun and playable. It's usually rough but it's suppose to be a proof of concept.
This is where games made at game jams usually stay at. Quick implementations, dirty hacks, and messy prototypes to get it working.
This is usually the funnest part of a project, throwing it together and having it do what you want it to do.

## 2. Make it Right

Getting it working usually means it's not well architected, unless you really know what you're doing.
Making it right usually means refactoring to make the code readable, applying better design patterns, fixing all those weird bugs, and more.
Sometimes, the behaviors are faked to get it working!

This is an example of what I need to make right for my game, TwoKinds Online. 
I added new tree chopping and rock hitting mechanics so that players can collect wood and rocks.
It fakes the server side checks, so there's no limit on the number of resources available, and you can hit the same tree forever. 
Making it right means I need to finish the implementation, and make it so the trees have a set number of wood you can collect, controlled by the server side.
I will probably go into more depth how the system works in a later blog post.

## 3. Make it Fast

The most important part. Once it works right, it still may not be fast. 
Making things right, in general, should make everything run better, but the goal there is to make it easier to update, maintain, and add more later.
This is where we return back to hacks to speed up things. 
Even with the right frameworks, there's speed issues, and it's only after cleaning up the implementation the cause can be found and properly dealt with. 
Pre-mature optimization is bad because it can lead to a lot of wasted work, make it harder to add things later, and can be fixing a symptom, not a cause of an issue.


## Optimization
What lead to this blog post was a question about what is game optimization.
A lot of games are released as buggy messes, and that is usually due to tight schedules and not enough time to to clean up and speed up the the game code.
For games, speed matters a lot because games have to process and render many times a second.
First implementations are usually done in a quick and naive way, the make it work step.
After a bit of testing and implementing other related systems, we can take a step back and see there are improvements we can do. 
This is optimizing, the make it right and make it fast steps.


There's a lot of design patterns and principles to help improve quality, but sometimes you have to get it working first. 
What's nice is, some chunks of the code/game can be in different stages of the process, especially if the systems are independent from each other.

## Conclusion

My code usually starts as a mess and I have to iterate over it a few times. 
I am very much for prototype first and using code as a scratch pad to try things.
More structure is probably required in the future but this is a good process if you need to make some thing quickly. 
Just get it to work. And then improve on it.
