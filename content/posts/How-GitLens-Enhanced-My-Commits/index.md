---
title: How GitLens enhanced my commits
date: 2021-01-08T16:30:00+03:30
lastmod: 2021-01-08T16:30:00+03:30
tags: ['Git', 'GitLens', 'VS Code']
cover:
    image: gitlens-logo.png
    alt: GitLens
    relative: true
---

I've been using [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) on VS Code since always! The reason I Installed GitLens is being one of the most popular and recommended extensions on the marketplace. But recently I've noticed how its [current line blame](https://github.com/eamodio/vscode-gitlens#current-line-blame-) feature has made my whole committing process much better.

Of course, I knew about [Git blame](https://git-scm.com/docs/git-blame) long before even GitLens came into existence. Although it's a great tool to exploit git history, It's not handy and easy to use and so it's not commonly used. Or at least, not as common as seeing the current line blame at all times.

There are lots of conventions and tools to enhance git usage with the concept of clean history in mind. If you haven't seen much yet, I suggest you take a look at these for instance.

- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) or just google "semantic commits"
- [Git Flow](https://nvie.com/posts/a-successful-git-branching-model/) (If you liked this one, be sure to check out [the cheat sheet](https://danielkummer.github.io/git-flow-cheatsheet/) as well)
- [Gitlab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)

Now let's think about why did people come up with these ideas in the first place? What are the problems they're trying to solve? And why don't some of the largest open-source projects, like [Linux](https://git.kernel.org/) and [Kubernetes](https://github.com/kubernetes/kubernetes), use them?

One of the most important jobs these tools and concepts are trying to do is keeping a clean history, if not the only job. I've followed some of their practices in the past. But I have to say, despite being conscious about the importance of clean histories and the efforts I've made to keep it that way, I never had a deep understanding of why does it matter or how it should be.

But after using VS Code with GitLens for quite some time, I gradually grew a habit of looking at the last commit message of the current line I was working on to understand why the last author wrote it. And then I tried to think about the next developer reading my commit messages like I do and optimizing the commit messages to be more meaningful without realizing it.

But it's not easy to write a few words to describe a bunch of SLOC. Still trying to produce better commit messages, I felt the need to step further than the message itself and break my changes into smaller pieces resulting in commits with fewer changes. subconsciously I started to follow the [UNIX philosophy](https://en.wikipedia.org/wiki/Unix_philosophy). Make each commit do one thing well.

As a result, I found my commits precise, concise and easy to review. Now the reviewer can follow my thoughts on how I did the job. And as the author, I can make the changes happen easily if any requested.

And last but not least many thanks to [Eric Amodio](https://www.amod.io/) for creating this amazing tool.

P.S. To be honest, when I think about it now, It's all so intuitive and plain simple that I doubt whether it's useful to share or not. Anyway, I'm happy to share the story.
