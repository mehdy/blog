+++
title = "The Battlefield"
date = "2017-05-23"
categories = ["Python"]
keywords = ["Python", "TehPUG", "Django", "Project"]
tags = ["Python", "TehPUG", "Django", "Project"]
thumbnailImagePosition = "top"
thumbnailImage = "/images/2017-05-the-battlefield-cover-800.jpg"
coverImage = "/images/2017-05-the-battlefield-cover.jpg"
coverMeta = "out"
+++

Battlefield is a project that I've started in [TehPUG](http://tehpug.ir). you can read the story behind it and see how I decided to start this project [here](2017/05/the-tehpug/).
<!--more-->

So far till now I experienced some projects and activities that didn't work out as I expected. I asked my self what are the requirements to activate and motivate TehPUG. I came up with a few answers...

* It should be suitable for everyone. from the very beginner that learned something about python today to the python expert. they all should be able to participate.
* It should be able to engage as many people as possible
* It should be endless. it shouldn't be a project that we do for a while and when it's done it's there are nothing else to do.
* It should be fun and attractive and also useful and helpful

So based on these criteria I came up with an idea. A battlefield. A field for robots to fight.

## The idea
There's a platform that has a pluggable system that as many games as we want. Games like mazes, capture the flags and etc. It can have as many leagues and tournaments as we want. Now anyone who wants to have fun and challenge its programming skills can sign up and create a robot. Give the robot a program to guide it through a match. Register the robot in different leagues and achieve trophies. This is the basic idea.

#### why this is a good idea?
Well if you think about it, it covers all of the criteria I had. It's suitable for everyone in any level. It has no limitation on participation. The challenges are endless because there are endless games. It is fun and attractive also helpful. So I think anyone who walks into the TehPUG can create a robot and struggle with it. if he/she got bored. there are other games. bored again? create a new game! bored again? contribute to the main project. So I think it's pretty a good idea.

## The architecture
A battle field is where many fights are going on and we need a supervisor for these fights.
### The Ares
Ares is the greek god of war. and apparently its the god of our wars too :))
Ares is the supervisor who manage games, leagues, tournaments, robots, users and matches. It's agnostic about a game rules and how robots works in a match. it just create it, run it and store the result. it's the core of Battlefield. Ares is written in [Django](https://www.djangoproject.com/) with a [PostgreSQL](https://www.postgresql.org/). Here is the [source code](https://github.com/tehpug/ares).

### The Games
Games are codes that know the logic and how to run a game and instruct and manage the robot during their fights and how to apply rules and calculate scores. Their created and ran by Ares. Games haven't been developed yet but I assume they'll be written in pure python. The communication between games, Ares and robots are through [Celery](http://www.celeryproject.org/) on top of a messaging infrastructure like [RabbitMQ](https://www.rabbitmq.com/)

### The Robots
Robots are also codes that know how to play a certain game and work with the game engine. The robots can be written with anything user wants. from pure python to the most sophisticated frameworks and libraries.

## Final words
I talked about the idea for the first time about 3 months ago in pug session. But I've been working on battlefield for about a month now. I've implemented most of the basic needs we have for the first version to be released.
I'm trying hard to engage other people in the project and I'll be more than happy if you [contribute to the project](https://github.com/tehpug/Ares).

Also as always I'd be happy to have your comments.
