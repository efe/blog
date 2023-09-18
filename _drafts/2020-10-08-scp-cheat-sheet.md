---
layout: post
title: "scp Cheat Sheet"
description: scp (secure copy) is a command-line utility that allows you to securely copy files and directories between two locations.
---

scp (secure copy) is a command-line utility that allows you to securely copy files and directories between two locations.

- Copy a local file to a remote

```sh
scp my_local_file.txt ubuntu@efe.me:/home/ubuntu
```

- Copy a remote file to a local

```sh
scp ubuntu@efe.me:/remote_file.txt /home/ubuntu
```

- Copy between remotes

```sh
scp ubuntu@efe.me:/source_file.txt ubuntu@oge.me:/files
```
