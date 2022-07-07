---
title: Issue when changing the hexo post name
date: 2022-07-07 14:50:55
tags: [Hexo, issue]
categories:
    - [issue]
description: Renaming issue
---

Today I found that even though I was able to open a post name `My first post using hexo framework for blog`, it couldn't be open on the remote server.

After digging into the problem, I found the issue is that the original post name is `my first post using hexo framework for blog`, where **M** is lowercase before.

So the issue is that git is by default case insensitive, so the folder in `.deploy_git` is always the lowercase one, and the website can't open requests for the uppercase one. Even if I change the name to uppercase, git still thinks they are the same. So I have to manually untrack and track again (or by git mv to rename).

In the future, it's better to just change the `title:` in the front matter and leave the post Markdown filename unchanged
