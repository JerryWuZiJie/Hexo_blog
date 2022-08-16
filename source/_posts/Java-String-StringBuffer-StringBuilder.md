---
title: 'Java String, StringBuffer, StringBuilder'
tags:
  - Java
categories:
  - - programming
    - Java
description: Difference between the three
date: 2022-07-20 20:40:47
---

`String` is immutable. When you try to change the value of a `String`, it actually creates a new `String` object. `StringBuffer` and `StringBuilder` are mutable, while `StringBuilder` is thread-safe and `StringBuffer` is not.

BTW, String is not strictly immutable, one can change its value by the following way:

```java
String s = "abc";

Field value = s.getClass().getDeclaredField("value");
value.setAccessible(true);
value.set(s, "abcd".toCharArray());

System.out.println(s);  // abcd
```

## Reference

- <https://www.bilibili.com/video/BV1yT411G7ku?p=1&vd_source=99a1bb3a7187eeea1a5ee8e957c968a7>
