---
title: Java Hello World!
date: 2022-07-08 14:29:26
tags: [Java, demo]
categories:
    - [programming, Java]
description: Hello World in Java
---

This post demonstrates how to write a simple Java program.

1. create file end with `.java`
2. writes the following code

    ``` java
    public class Hello{
        public static void main(String[] args){
            System.out.println("Hello World!");
        }

    }
    ```

3. run `javac filename.java` to compile. If successful, a new file name `filename.class` will be created.
4. finally, run `java filename` to run the program.

Some elaboration:

- `public` is an access modifier indicating that the class and method can be accessed by others. `static` means it's a static method that is accessible without creating an instance of the class. `void` means the method doesn't return anything. `main` is the entry point for any Java program. When the program start, it looks for the main method and executes it. `System.out.println()` is a built-in method call. `Hello World!` is a string literal.
- Java can be considered as both interpreted and compiled language. It compiles the source code into `.class` files when you run `javac`, and JVM interprets the compiled code when you run `java`.
