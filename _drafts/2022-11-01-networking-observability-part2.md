---
layout: post
title: "Networking for Dragon Game Framework : Data Optimization"
date: 2022-11-01 03:00:00 -0800
categories: programming
---
{% include post-styling.md %}

This is part 2 for [Networking for Dragon Game Framework : Observability]( {%post_url 2022-11-01-networking-observability-part1 %} )  

Last [Dragon Game Framework (DragonGF)](https://github.com/judah4/MMO-Dragon-Game-Framwork), an MMO networking library for a while now, and I need to improve the observability of the data. Time to build a Unity editor window!

## Fixed Point Decimals and Data Packing

We now have a Position as 3 fixed point decimals (32 bit numbers) to represent a large but smaller game space which we send updates for at 10 Hz (10 every second).
Each message contains a byte for message type, 4 bytes for the entity id, and 2 bytes for the component id. If we add it all together, each message is 4+4+4+1+4+2 = 19 bytes, plus a little more overhead. At 10 Hz, that is 190 bytes per second per moving entity. With 100 moving entities, that's now 19 Kilobytes per second for only position which is a lot better!

