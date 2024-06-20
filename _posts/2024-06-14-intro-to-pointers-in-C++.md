---
layout: post
title: Intro to Pointers in C++
description: A pointer overview for beginners
date: 2024-06-14 21:20:00 -0800
tags: Blogging
---

## What are pointers?

If this is the question in your head right now, you've come to the right place. After reading this blog, you will be able to answer the question.


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
<div style="text-align: center;">
    <img src="/assets/x004898.png" alt="variable">
</div>


### What is a pointer?

To put it simply, a pointer is just a variable that stores the memory address of another variable or an object (you can leave this for my upcoming object-oriented programming blog). In other words, we say a pointer is pointing to a space in computer's memory (RAM) that is allocated for a data type which can be an integer (int), a double and so on.

For example:
```cpp
  int our_number = 10;
```
The variable `our_number` has the value of an integer 10 and an address of, let's say, x004050. In order to get the address of a variable in c++, we just need an operator called the ampersand `&`. (put it before the variable name to get the address of that variable). 
* To store the address of a variable, we need a pointer. So, how do we declare a pointer in C++? How do we assign the address of a variable to a pointer? The following code fragment will show you how. 

```cpp
  int our_number = 10;
  int* ptr; // Here is how you'd declare a pointer.
  ptr = &our_number; // Here is how you'd assign an address to a pointer.
  cout << "Address of our_number: " << &our_number << endl;
  cout << "Address of our_number: " << ptr << endl;
  cout << "Value of our_number: " << our_number << endl;
  cout << "Value of our_number: " << *ptr << endl; // *ptr means dereferencing the pointer, we'll talk about this
  cout << "Address of the pointer: " << &ptr << endl; 
```
* Now, the pointer `ptr` is holding the address of `our_number`, in other words, the value held by `ptr` is the address (just think of it as a number) of `our_number`.
* So, how do we access the value of `our_number` via the pointer `ptr`? Easy peasy lemon squeezy, you just need to dereference the pointer using this syntax `*ptr`.
* Running the code above, you may notice that there is a difference when we print the `ptr` and `&ptr`. Why so? Let's look at the output of the code fragment above:

![output of example 1](/assets/output_of_1st_example.png)

The image shows that the outputs of `ptr` and `&ptr`, which are the value and address of `ptr`, are different. Why so? The following image would help you.  

