---
layout: post
title:  "Notes: Building microservices of Sam Newman, Part I benefits"
date: 2015-11-01 16:20:03
categories: microservices
---
I have been working for three years as a Software Developer and in all companies I have found the same mistake in software products, when software are so big is very hard to maintain, the main reason is that technical debt increase every month and there is no willingness to clean the house before continue.
When I saw those kind of software, the pattern is the same, all are implemented as a monolithic code with high coupling.

So I decided to learn and apply the approach of Microservices.

Architecture oriented to Microservices is different than oriented to the functionality, because its proposal is divide a business domain in independent projects that are autonomous and each one resolve a specific problem related its concern, the trade-off of separation depends of a variety of aspects such as  cohesion, organization, teams, technologies, scope of each functionality, etc.

In first chapters, Sam Newman speaks about the architecture and its key benefits:

* **Technology Heterogeneity**: Using the right technology for each job, or improve individually performance.

* **Resilience**: You can isolate the problem, and the system can carry on working. (Degrade funcitonality).

* **Scaling**: It is not require to scaling everything together, Just the small one part with overall performance. Also scaling on demand critical parts reduce operation costs.

* **Easy of deployment**: Features can be get out customer faster, because are independent.

* **Organizational aligment**: To be more productive, with smaller teams reducing the side of codebases.

* **Composability**: Reuse functionality for different purpose, for example variety of channels (mobile, desktop..).

* **Optimizing for Replaceability**: Avoid problem like a nasty leagacy code, because is to big and risky to been replaced.
 
