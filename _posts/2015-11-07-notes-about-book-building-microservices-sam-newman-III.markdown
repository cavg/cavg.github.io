---
layout: post
title:  "Notes: Building microservices of Sam Newman, Part III DB and Sync"
date: 2015-11-07 10:41:04
category: microservices
---
Integration is a very important topic in Microservices, because define the way of how diferent services are going to communicate to others. Other important concept is that integration and interfaces that are exposed to be consumed it has to be technology-agnostic so these days the answer is API REST, for modeling I strongly suggest 'API Design Design, Crafting interfaces' by API Gee

The shared DB: Is common when we design a monolithic architecture allow that differents services perform CRUD operations out of its domains, the problem with this approach is that if we change our schema impact in several services that perform operations directly in our database and other releated concept is that our integration interfaces shouldn't have to expose implementation details, means for example that one service could be use Document DB and other Relational Database, in that case if we hide implementations details and communication happens only using standar interface it haven't be a problem.

Sync or Async? sync approach means that a clients initiates a request and wait until response (is blocking operation) and the other hand async is pattern oriented to Event-based so the artifact that make a call it not required to know how to handle the response expecting other parties knows what to do, so Event-Based is more decoupled way, other really good think is that event based allow to subscribe several artifacts to an event.
The important think if you choose some aproach is in case with async you have to run another system to those messages, something like Message Broker (Ex RabbitMQ), so any decision have consecuences. 

Orchestration vs Choreography
With orchestration manner we have to knows and govern the hole process, so it have to know all the effects of one operation, but with choreography  we only have to emit some signal that notify to all subscribers, so is more naturally deacoupled approach because each service is smart enough to understand which is its role in the whole system.
