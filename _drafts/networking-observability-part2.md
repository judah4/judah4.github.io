---
layout: post
title: "Networking for Dragon Game Framework : Data Optimization"
categories: programming
---
{% include post-styling.md %}

This is part 2 for [Networking for Dragon Game Framework : Observability]( {%post_url 2022-11-01-networking-observability-part1 %} ). These are my ramblings as I work through problems with [Dragon Game Framework (DragonGF)](https://github.com/judah4/MMO-Dragon-Game-Framework), an MMO networking library.

## Fixed Point Decimals and Data Packing

We now have a position as 3 fixed point decimals (32 bit numbers) to represent a large but smaller than previous game space which we send updates for at 10 Hz (10 updates every second).
Each message contains a byte for message type, 4 bytes for the entity id, and 2 bytes for the component id. If we add it all together, each message is 4+4+4+1+4+2 = 19 bytes, plus a little more overhead. At 10 Hz, that is 190 bytes per second per moving entity. With 100 moving entities, that's now 19 Kilobytes per second for only position which is a lot better than the previous estimated 31 KB/s!

Is it possible to improve this further with compression and more data packing? Probably yes.

## The Name

Originally, I prototyped it as just MMO Game Framework in response to the issue with [SpatialOS and Unity](https://massivelyop.com/2019/01/11/improbable-unity-spatialos-drama-continues/) back in early 2019. In 2022, I revisited the project and wanted to give the it a fun name. I like dragons so it's became MMO Dragon Game Framework or DragonGF for short, also known as Dragon Girlfriend.

## What's Next?

A game demo! I'm working on a simple pirate ship game that will show the basics of what the project can do. I'll also take suggestions on what else to build with it. Now that I'm thinking about it, I should make a simple fantasy RPG with it.
