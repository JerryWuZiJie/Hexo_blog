---
title: Java Setup
date: 2022-07-07 16:51:05
tags: [Java, tutorial]
categories:
    - [setup]
    - [guide]
    - [programming, Java]
description: Setup JDK8
---

It's been a while since I set up Java last time (around 2015). After that, I use Java intermittently, but only in ready-to-go environments like [LeetCode] and [replit](https://replit.com/). Now I decide to learn Java again and from the very beginning. This post will include how to set up the Java environment so it's ready to code.

> OS: Windows 10

## Install JDK8

The reason that I don't use the latest JDK (Java Development Kit) is that JDK8 is the most popular among enterprises.

Relationship between JVM, JRE, JDK: JDK includes JRE includes JVM

1. Download [JDK8](https://www.oracle.com/java/technologies/downloads/)
2. configure Environment Variables*
   1. create a new environment variable `JAVA_HOME`, the variable value is the directory of the JDK (something like `path/to/java/jdk1.8`)
   2. add the following to the `Path` variable:

      ``` bash
      %JAVA_HOME%\bin
      %JAVA_HOME%\jre\bin
      ```

3. open command prompt and type `java -version` to check if the JDK is installed correctly

\* Difference between User Variables and System Variables:

> System variables are shared for all users, but user variables are only for your account/profile <sup>[[1]](<https://stackoverflow.com/a/4477681/13720936>)</sup>
>
> Environment variables are 'evaluated' (ie. they are attributed) in the following order: System variables -> Variables defined in autoexec.bat -> User variables <sup>[[2]](https://stackoverflow.com/a/16305526/13720936)</sup>

## Uninstall JDK8

In `Environment Variables`, find `Path`, inside you will find Java's directory. Go to that directory and just delete it. Then remove it from the `Path`, and delete Environment Variable `JAVA_HOME`.

## Reference

- [狂神说Java](https://www.bilibili.com/video/BV12J41137hu?p=17&spm_id_from=pageDriver&vd_source=99a1bb3a7187eeea1a5ee8e957c968a7)

1. [StackOverflow](https://stackoverflow.com/a/4477681/13720936)
2. [StackOverflow](https://stackoverflow.com/a/16305526/13720936)
