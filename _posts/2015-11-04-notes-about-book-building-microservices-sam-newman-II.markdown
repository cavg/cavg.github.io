---
layout: post
title:  "Notes: Building microservices of Sam Newman, Part II bases"
date: 2015-11-04 22:04:04
category: microservices
---
Before to start deeply in microservices, and after to describe the first benefits in previus post, Sam explains how a good Microservices looks like.

The two main concepts behind a good microservies are:

* Loose coupling: When services are loosely coupled a change to one service should not require a change to another. The only interaction between two services it has to be as little as it needs, reducing the call from one service to another.

* High cohesion: Releated behavior sitting together, because if we have to change in a shared behavior we have to change it in diferents places, if your think a business domain like a organization division it should be more natural and easy to determinate how to split the traditional monolithic architecture.

Eric Evans's introduces the concept called "bounded contexts" means an specific domain (busines niche derivated of the product to develop) consists of multiple bounded contexts where each one it not have to communicate outside of its context, meaning it have its own reason to exist.






