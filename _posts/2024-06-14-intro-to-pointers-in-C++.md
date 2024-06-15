---
layout: post
title: Intro to Pointers in C++
description: How to build a blog for free, using GitHub Pages.
date: 2024-06-14 21:20:00 -0800
tags: Blogging
---

## What are pointers? What are they used for? 

If these are the questions in your head right now, you've come to the right place. After reading this blog, you will be able to answer these questions.


> *Disclaimer: this blog is not an academic article, there will be many simplified terms and concepts just so you can grasp the idea quickly.*

---

### Let's get started

To understand what a pointer is, you need to understand what a variable is and how it looks in the memory.

* First, you just need to know that a variable is name (you can name it whatever you want) that represents a space in the memory. The size of that space is set based on the data type you set for the variable.

> *Note: int (integer) and double are data types that you likely encounter as a beginner. You just need to remember that int is a number that must not have a decimal point and places. Whereas, a double is number that has a decimal point and decimal places*

For example:
```cpp
  int micky_mouse;
```

When you declare the variable named `micky_mouse` with a data type of an integer as shown above, the computer will set up a space with a size of an int (4 bytes) in the memory.

Whenever you write `micky_mouse` in your code, the compiler will understand that you're referring to the space I've just mentioned.

* Second, a variable has 2 parts:
  * its content (can be anything, even another address of another variable)
  * its address in the memory

I'll set our `micky_mouse` as the number 10:
```cpp
  micky_mouse = 10;
```
![A variable](/assets/x004898.png)


### What is a pointer?

Pointer is just a variable that stores the memory address of another variable. We can also say that a pointer is pointing to a space in computer's memory (RAM) that is allocated for a data type which can be an integer (int), a double and so on.

For example:
```cpp
  int our_number = 10;
```
