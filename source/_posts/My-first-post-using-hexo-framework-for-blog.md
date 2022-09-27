---
title: My first post using hexo framework for blog
date: 2022-07-04 22:18:15
tags: [Hexo, tutorial, framework]
categories:
    - [setup]
    - [guide]
description: First post, setting up Hexo
---

Hi, this is Jerry (Zijie) Wu! I decided to start writing blogs. And after some quick research, I found that hexo seems to fit my needs. It can be deployed on GitHub so I don't have to rent a server. I've also considered using LinkedIn as a blog platform, but seems like not many people are doing that and it doesn't look "geeky."

I will mainly use the blog to write about things related to my major (Electrical and Computer Engineering) and hope to share my knowledge and experience with others (if anyone ever visits).

## Setup Hexo

In the following, I will briefly talk about how to set up Hexo and deploy it on GitHub and how to use it.

### Install

1. install node.js
2. open terminal
    1. `npm install hexo-cli -g` to install hexo
    2. `mkdir`*`directory`* to create a new directory for a new Hexo project
    3. `cd`*`directory`* to enter the new directory
    4. `hexo init` to initialize a new Hexo project
    5. `hexo server` to start a server on a local host (hexo s for short)
    6. `hexo new`*`post_name`* to create a new post (hexo n for short)
    7. `hexo clean` to clean the static files
    8. `hexo generate` to generate new static files
    9. `npm install hexo-deployer-git --save` to install the git deployer
3. create a new repository on GitHub, the name must be `githubusername.github.io`
4. in the _config.yml file, and modify the **deploy**** section:

    ``` yml
    deploy:
        type: git
        repo: https://oauth2:yourtoken@github.com/*****.github.io
        branch: master
    ```

    remember **not** to include *yourtoken* in a public repository.

5. run `hexo deploy` in terminal to deploy to GitHub (hexo d for short)
6. now you can access your blog at `https://githubusername.github.io` (wait for a few minutes if it doesn't work)

### Usage

- `hexo n "title"`: create a new post
- `hexo s`: start a server in a local host
- `hexo cl`: clean the static files
- `hexo g`: generate the static files
- `hexo d`: deploy to GitHub

## Reference

- [Step-by-step Hexo installation guide (Chinese)](<https://www.bilibili.com/video/BV1Yb411a7ty?spm_id_from=333.999.0.0&vd_source=99a1bb3a7187eeea1a5ee8e957c968a7>)
- [Hexo Youtube Tutorial](https://www.youtube.com/watch?v=Kt7u5kr_P5o&list=PLLAZ4kZ9dFpOMJR6D25ishrSedvsguVSm)
- [Markdown Basic Syntax](https://www.markdownguide.org/basic-syntax/)
