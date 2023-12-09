---
title: "Distributed Systems in One Lesson - Notes"
date: "2019-02-14 22:52:55"
category: "tech"
tags:
  - system design
  - distributed systems
---

With more and more people getting into development, the number of people who are working with distributed systems are

Tim Berglund

What is a Distributed Systems ?

> A collection of independent computers that appear to users as one computer
> -- Andrew Tannenbaum

In addition to the defintion above, he defines these three key characteristics 

1. The computers operate concurrently
1. The computers fail independently
1. These computers do not share a global clock

Let's look at some examples

- Amazon.com
- Cassandra database - horizontall scalable non-relational database
- My Computer - X

Storage: Relational/Mongo, Cassandra, HDFS (Distributed File System)
Computation: Hadoop, Spark, Storm
Synchronization: NTP (Network Time Protocol), Vector Clock (Mathematically rigourous)
Consensus: Paxos (an algorithm), Zookeeper (offers some services)
Messaging: Kafka

https://player.oreilly.com/videos/9781491924914


dahos@webmail24.top / Lear4free