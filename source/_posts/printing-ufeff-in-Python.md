---
title: printing \ufeff in Python
tags:
  - issue
categories:
  - - issue
description: When using utf-8 to decode in Python, some files will include "\ufeff" at the beginning of the file
date: 2022-10-09 20:33:19
---

When using utf-8 to decode in Python, some files will include ```\ufeff``` at the beginning of the file.

This is because the file is encoded in utf-8 with BOM (Byte Order Mark). So we need to use ```utf-8-sig``` to decode the file.

## Reference

<https://www.cnblogs.com/lansan0701/p/10600220.html>
