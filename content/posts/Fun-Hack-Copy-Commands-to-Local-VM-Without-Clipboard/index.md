---
title: "Fun Hack: Copy commands to a local VM without clipboard"
date: 2017-07-14
lastmod: 2020-10-17T10:10:00+03:30
tags: ['Fun', 'Hack', 'Linux', 'VM', 'Netcat', 'SSH']
---

I was following an instruction to deploy an application on a Virtualbox VM and I wanted to execute the long commands. By default it’s not possible to copy those command into the VM. VirtualBox has a shared clipboard feature which I tried to get it working but it didn't happen so I didn’t dig into it and I came up with a funny hack :D
I sent the commands through a socket :)

## The Hack

`nc` or `netcat` is usually installed by default in some linux distros. So I opened a socket with `nc` on my host using the following command

```bash
nc -l 4567 # listen on 4567
```

and I connected to the socket from the VM by

```bash
nc 192.168.1.2 4567 | tee cmds.sh
```

the first part (before pipe) opens a socket to the remote address and the second part (after pipe) writes the received texts to a file named `cmds.sh`.
and then obviously I ran the commands I wanted via

```bash
sh -C cmds.sh
```

A fun hack ;)

P.S.
Now that I think I could just open an ssh connection and execute the commands remotely :))
