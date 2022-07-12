---
title: setup IME for Sogou Pinyin
description: Setup Sogou in Windows and disable 
date: 2022-07-12 01:43:57
tags:
    - input method
    - chinese
categories:
    - setup
---

As a native Chinese speaker, I sometimes need to type Chinese and thus need a Chinese input method editor (IME) on my Windows. The one that's most popular in China is Sogou. The installation and usage is straightforward. Yet itself has a lot of key bindings that I'd never use, and those key bindings conflict with vscode shortcuts (since vscode has **a lot of** shortcuts). So this post is about how to disable those shortcuts, and how to set up different IME for different applications, a nice feature that Windows provides

Environment: Windows 10

## Sogou Settings

1. open settings of Sogou by right-clicking on the icon in language bar
2. [optional] *常用* -> *默认状态*, select *隐藏状态栏*
3. [optional] *按键*, unselect *系统功能快捷键*

## Windows Settings

1. open Windows settings, go to *Time & Language* -> *Language* -> *Spelling, typing, & keyboard settings* -> *Advanced keyboard settings*
2. choose the default input method
3. choose *Let me use a different input method for each app window*
4. click *Input language hot keys*, disable any key binding that you don't want to use
 