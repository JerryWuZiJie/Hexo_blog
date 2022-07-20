---
title: Java equality operator
description: ==
date: 2022-07-20 18:32:59
tags:
  - Java
  - issue
categories:
  - [programming, java]
  - [issue]
---

- `==` only compares if two objects are pointing to the same address (similar to the Python "is" keyword)
- `equals()` method is used to compare if two objects' content (or other user-defined behavior) are equal
- primitive type doesn't have methods, so they can only be compared using the `==` operator. If two primitive types have the same value, they are pointing to the same location in the memory, therefore sharing the same address, and that's why the `==` operator works. When comparing a primitive type to a non-primitive type, Java will unbox the non-primitive type to a primitive type, and then compare the two primitive types.

## Example

1. primitive (decimal) and BigDecimal

    ```java
    float a = 10000000000000000000f;
    float b = a + 1;
    System.out.println(a == b);  // true

    float c = 0.2f;
    double d = 0.2;
    System.out.println(c == d);
    System.out.println(c);
    System.out.println(d);
    ```

    The reason is related to the underlying representation of floating-point numbers. To avoid that, use BigDecimal class.

    ```java
    BigDecimal a = new BigDecimal(0.3);
    BigDecimal b = new BigDecimal(0.2);
    System.out.println(a.subtract(b));  // 0.099999999999999977795539507496869191527366638183593750

    BigDecimal c = new BigDecimal(Double.toString(0.3));
    BigDecimal d = new BigDecimal(Double.toString(0.2));
    System.out.println(c.subtract(d));  // 0.1

    BigDecimal e = BigDecimal.valueOf(0.3);
    BigDecimal f = BigDecimal.valueOf(0.2);
    System.out.println(e.subtract(f));  // 0.1
    ```

    "The results of `BigDecimal(double val)` can be somewhat unpredictable" according to the official documentation. The best way to do it is using a String or using the `valueOf` method which calls the toString method inside.

1. String

    ```java
    String s1 = new String("abc");
    String s2 = "abc";
    System.out.println(s1 == s2);  // false
    System.out.println(s1.equals(s2));  // true

    String s3 = s1.intern();
    System.out.println(s2 == s3);  // true
    ```

    When Java runs `new String("abc")`, it actually creates two objects: `"abc"` which will be stored in String Pool, and a String object which will be stored in Heap. Thus comparing s1 and s2 is comparing two different objects reference. However, `intern()` method returns the reference to the String Pool, and that's why s1 and s3 are equal.

1. Integer

    ```java
    Integer a = 100;
    Integer b = 100;
    System.out.println(a == b);  // true

    Integer a2 = 1000;
    Integer b2 = 1000;
    System.out.println(a2 == b2);  // false

    Integer a3 = new Integer(100);
    Integer b3 = new Integer(100);
    System.out.println(a3 == b3);  // false
    ```

    There is a `valueOf(int i)` method for the Integer class, which returns a cached Integer object if the value is between -128 and 127. However, creating an Integer object directly would not use the cached object.

    ```java
    Integer a = 10;
    float b = 10f;
    System.out.println(a.equals(b));  // false
    ```

    The `Integer.equals(Object obj)` method always returns false if obj is not an Integer object.

## Reference

- <https://www.bilibili.com/video/BV1yT411G7ku?p=2&vd_source=99a1bb3a7187eeea1a5ee8e957c968a7>
- <https://zhuanlan.zhihu.com/p/52710835>
- <https://mp.weixin.qq.com/s/EHNlUIjEhTgp2Q7JT9pscQ>
