---
layout: post
title:  "Rant about real-time Ray Tracing"
categories: [coding]
author: "xeno"
---

If you're developing a 3D graphical app and aiming for a 10% improvement and a 10x difficulty scale compared to the standard rasterization approach, you should try implementing real-time ray tracing. God Bless you're fortunate enough to have have access to a decent IDE that supports shader debugging, such as XCode and the Metal API. However, if you don't have such a setup, be ready to spend countless hours in troubleshooting CPU <=> GPU synchronization problems, padding rules, and silent errors. Note: even with a good setup you're restricted to a specific platform and can't share the code with someone who doesn't have the required hardware and software.

Some may argue that the raster approach requires significant **hacking** with lightning, shadows, and reflections. On the other hand, ray tracing remains extremely difficult to implement due to its high resource requirements, requiring numerous **optimizations**, such as creating BHV, acceleration structures. Even after implementing them or utilizing a built-in API, it's impossible to guarantee decent **real-time** performance.

Real-time ray tracing doesn't worth the effort. You should always prioritize the raster approach. However, there's hope: you can generate ray tracing **offline** and create a video. Offline rendering doesn't have performance problems and doesn't require using two separate programming languages and some complex GPU/CPU synchronization wizardy.