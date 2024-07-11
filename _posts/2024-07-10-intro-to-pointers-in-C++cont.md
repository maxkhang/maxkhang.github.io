---
layout: post
title: Intro to Pointers in C++ cont
description: A pointer overview for beginners
date: 2024-07-10 21:11:00
tags: Blogging
---

# Introduction to pointers in C++ (II part)

### Welcome to the next part of the series, 'Introduction to pointers in C++.'

>*Please see the I part of 'Introduction to pointers in C++' in the `Blog Archive` at the top right corner if you haven't.*

In this article, we will discuss a very interesting characteristic of pointers. It is Pointer Arithmetic!

### What is Arithmetic? 

You might have heard and learned about this topic in high school and also imagine what arithmetic is now. Is it about mathematical operations: `+, -, *, /` ?

Yes, it is! To be more specific, arithmetic is a branch of mathematics that includes numerical operations like addition, subtraction, multiplication and division but does not exclude taking logarithms, exponentiation and so on. However, multiplication and division cannot be performed in the pointer manner.

You have already been introduced to the idea of arithmetic. Nevertheless, how is it related to the topic we are discussing?
I'll show you right now.

### Pointer Arithmetic
  ### ** Prefix and Postfix increment/decrement
- Before jumping into pointer arithmetic, we need to talk about `prefix and postfix increment/decrement.`

>*If you're already familiar with this, you can ignore this part and get right into the pointer arithmetic part below*

- First, you might have yet to hear about increment or decrement in C++. However, I'm certain that if you see this `++` and this `--`, you will have a general idea about what they are.

    - Increment `++` means adding 1 unit to the current object, number, or whatever it is.
    - Decrement `--` means subtracting 1 unit from the current object, number, or regardless of what it is.

      For example:
      
      ```cpp
         //This program increases and decreases the value of a number and prints the output to the console
        #include <iostream>
        using namespace std;

        int main()
        {
          int number = 9;
          int another_number = 9;

          number--;
          another_number++;

          cout << number << endl;
          cout << another_number << endl;
    
          return 0;
        }
      ```

      Output:
      
      <div style="text-align: center;">
    		<img src="/assets/output_of_increVsDecrement.png" alt="output3">
      </div>

The example shows that the values of `number` and `another_number` are changed as the value of `number` decreases by 1 unit and that of `another_number` increases by 1 unit. Now you should understand how increment and decrement or `++` and `--` work.

- Second, we should now discuss prefix vs. postfix. They are pretty tricky, but no worries; they are just words to distinguish the increment and decrement `++ and -` position and return different values (we will talk more specifically later).

    - Prefix: prefix means that the increment or decrement will stand right before the object, variable or whatever we are incrementing or decrementing.
      
      ```cpp
         int number = 9;
         ++number;
      ```
    - Postfix means that the increment or decrement will stand after the object, variable or whatever  is incrementing or decrementing.
      
      ```cpp
         int number = 9;
         number--;
      ```

- Now, let's examine this simple example to see how the difference between prefix and postfix influences the result we want to achieve.

	```cpp
  
	#include <iostream>
 	using namespace std;

 	int main()
	{
   		int number = 9;

  		int another_number = 9;

   		cout << ++number << endl;

      		cout << another_number++ << endl;

      		return 0;
  	}
 	```
	Output:
  
  	<div style="text-align: center;">
    		<img src="/assets/output_of_prefixVsPostfix.png" alt="output1">
        </div>
  
- The program above illustrates the differences between prefix and postfix increments. As you can see, I first initialize two variables with the same value, an `integer 9`. After the program is executed, the variable `number` value is incremented by 1 unit to 10, but that is not *visually* the case with the variable `another_number`.

- By visually, I mean the `another_number` is already incremented by 1, but the second `cout` statement did not show us its incremented value. Why is all of that? 

--> This is because the *prefix increment or decrement* returns the already incremented or decremented value, whereas the *postfix increment or decrement* returns the value before the increment. Let's look at the example below if you don't trust me. 

- Example: 

	```cpp
		#include <iostream>
		using namespace std;

		int main()
		{
			int number = 9;

			int another_number = 9;

			cout << ++number << endl;

			cout << another_number++ << endl;

			cout << another_number << endl;

			return 0;
		}
	```

- Output:

	<div style="text-align: center;">
    		<img src="/assets/output_of_prefixVsPostfix(2).png" alt="output2">
	</div>

Trust me, guys. I did nothing but add another `cout` statement to print the value of `another_number` on the screen. This shows that the variable's actual value after the postfix increment is increased by 1. 

