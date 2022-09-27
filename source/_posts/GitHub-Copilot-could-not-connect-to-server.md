---
title: GitHub Copilot could not connect to server
tags:
  - issue
categories:
  - - issue
description: 'GitHub Copilot could not connect to server. Extension activation failed: "connect ECONNREFUSED 127.0.0.1:443"'
date: 2022-09-27 18:13:46
---

I'm currently back in China and found that I couldn't use GitHub Copilot in vs code. Every time I try to activate it I would get the following error:

```bash
GitHub Copilot could not connect to server. Extension activation failed: "connect ECONNREFUSED 127.0.0.1:443"
```

The issue is that the DNS is not set up correctly and GitHub Copilot is trying to connect to the wrong server. There are two solutions to fix this.

1. Change DNS to Google's DNS (8.8.8.8) and use Aliyun's DNS as backup (223.5.5.5)

2. Add the following line to the hosts file:

```bash
140.82.112.5 github.com
140.82.112.5 api.github.com
```

\# Extra tip: GitHub Copilot is free for verified students

## Reference

<https://blog.csdn.net/qq_42200700/article/details/125784101>
<https://zhuanlan.zhihu.com/p/522807476>
