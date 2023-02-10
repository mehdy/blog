---
title: Can You Solve This?
date: 2022-02-10T15:00:00+03:00
lastmod: 2022-02-10T15:00:00+03:00
tags: ['Problem', 'Algorithm', 'Fun']
cover:
    image: bus-passengers.jpg
    alt: Bus passengers
    caption: "[Image by pch.vector](https://www.freepik.com/free-vector/passengers-waiting-bus-city-queue-town-road-flat-vector-illustration-public-transport-urban-lifestyle_10173277.htm#query=city%20bus&position=9&from_view=keyword&track=ais) on Freepik"
    relative: true
---

Today when I was riding the bus I thought "would it be possible to efficiently utilize the seats so that each individual would sit as long as possible?". The short answer is for reality is probably "NO!" but let's have fun with the problem in theory at least :)

Let's say that we have a bus route with 50 stops and the distance between each consecutive pair is constant. The bus has 20 seats (Let's focus on one bus for now). Then at each stop (including the terminals) we get the data on how many people are getting on and at which stop they're getting off. At each stop tell each passenger to sit (optionally) or let them stay standing by default.

Write a piece of code that has a request/response interface (preferably via stdin/stdout). For each stop, you'll receive a JSON request to inform you of the new passengers and their destinations. And you must respond with a JSON response to suggest changes in the seating.  
When you assign a seat to a passenger, the passenger already sat there is automatically moves to a standing state.

```json
// Request
{
 "current-stop-id": [
  {"uid-for-each-passenger": "dest-stop-id"},
  ...
 ]
}

// Response
{
 "changes": [
  {"uid-for-each-passenger": "seat-id"},
  ...
 ]
}
```

And for simplicity let's assume that the stop IDs are always `X0..X49` and the seat IDs are always `Y0..Y19`.

There are two sample files below to use as input to test your code. Each file contains a JSON with 49 keys for each stop except the last one.

* [Sample-1.json](sample-1.json)
* [Sample-2.json](sample-2.json)

Have Fun! And share your code! :D (via email or in the comments. You can use [gist.github.com](https://gist.github.com) to share your code.)

P.S. I haven't solved myself yet :) But I'll try my best and I will write a judge to run the simulation and produce a report if I get at least a few responses to run them.
