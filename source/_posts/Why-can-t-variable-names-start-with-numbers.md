---
title: Why can't variable names start with numbers
date: 2022-07-08 18:23:02
tags:
  - variable
  - naming convention
categories:
    - [question]
description: No Description
---

Almost all programming languages I have seen so far don't allow me to start variable names with numbers. So I search it up, and found on StackOverflow that the reason is quite simple:

1. string of digits would be a valid identifier

    ``` c
    int 1 = 2;
    ```

2. if you allow the format of digits + alpha, then the following would still cause the problem:

    ``` c
    int 1f = 2;
    float a = 1f;  // a is 1.0 or 2.0?
    ```

## Reference

- [StackOverflow](https://stackoverflow.com/a/342192/13720936)
