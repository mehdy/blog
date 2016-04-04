---
layout: post
title: How I set up my blog and my personal email?
category: tutorial
tags: [blog, email, github pages, wordpress, openshift, cloudflare, jekyll, mailgun, IMAP]
comments: true
---
Although I had the [mehdy.net](https://mehdy.net) domain and an empty blog but I always was too tired to update it. But recently I decided to set up my blog and update my homepage and eventually create a personal email on my domain. So the story started a few days ago searching for the tools to do it.

Hosting service
===
I needed a place to host my blogs files and I was looking for somewhere cheap (because I just want to have a blog and some other static files for my personal homepage). Though I was using [wordpress](https://wordpress.org) on [openshift](https://openshift.com) before and it worked well for me but you know I was looking for new experiences :) and I chose [github pages](https://pages.github.com). I knew github pages before and even worked with it. But just for testing it out and I wanted to use it for real.

Blogging application
===
And I needed an application for blogging. As I said I was using wordpress before. Although I didn't have any special problem with it but..., you know..., come on!!! it has been written in PHP :)) anyway I was looking for something lightweight and powerful and I found it (Lie!! I knew it before:)) but as github pages I had just some testing experiences with it.

And BooM!! The great news is for me was "github pages support jekyll". So you don't need bother yourself with building your jekyll app and other stuffs. Just edit your jekyll app and write your posts and a simple commit and push is enough to be live on the internet.

Setting up domain
===
So till here I've chosen my hosting service and my blogging application. now I wanted to use my custom domain instead of ***username.github.io*** domain. So I just had to change a DNS record in my favorite DNS service, [cloudflare](https://cloudflare.com) (I'm using cloudflare since a long time ago and it has been great for me), It even gave an option to have a TLS connection for my blog.

Now everything's OK with my blog and I just have to write more posts :)

Personal email
===
Now I just need to set up my personal email on my domain. I really don't wanted a personal mail server to mange and maintain. So I searched a lot to find cheap and rather a free mail server service. and the result for me was [mailgun](https://mailgun.com). However it's not convincing but I'm okay with it for now. So I added my domain and set up the DNS records and set forward rule to my gmail. and finally setting my gmail client up to send mail from my personal mail. I could be too much happier if mailgun offered an IMAP for my email account. but anyway forwarding it is not bad too :)

finally I set up my blog and my personal email address on my domain and I suggest you to do it if you haven't done yet!

feel free to comment :)
