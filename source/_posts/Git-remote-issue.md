---
title: Git remote issue
tags:
  - issue
categories:
  - - issue
description: git pull/push to the remote takes a long time and fails
date: 2022-10-09 21:02:26
---

When I do a git pull today (in China), it took a while (about 10 secs) and I got ```fatal: unable to access 'xxxxxx': SSL certificate problem: unable to get local issuer certificate```. I tried to disable SSL verification by

```bash
git config --global http.sslVerify "false"
```

But I then got ```fatal: unable to access 'xxxxxx': Failed to connect to github.com port 443 after 21077 ms: Timed out```

Later on, I realized that I've opened the VPN, and even if I closed it the proxy setting is messed up. So to reset, one can do

```bash
git config --global --unset http.proxy
git config --global --unset https.proxy
```

Then I can do ```git pull``` and ```git push``` without any problem.

## Reference

<https://blog.csdn.net/m0_66695483/article/details/125036055>

<https://blog.csdn.net/csdn565973850/article/details/125785692>
