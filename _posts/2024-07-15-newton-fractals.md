---
layout: post
title: Creating Newton's fractal with C++
description: A project demonstrates how to generate Newton's fractal using C++
date: 2024-07-15 20:11:00
tags: Blogging
---

# Creating Newton's fractal with C++

## Welcome to my blog, I will walk you through the fascinating process of generating a Newton's fractal using C++. 

First, let me show you the result we want to get at the end. It is a beautiful self-similar pattern.

<div style="text-align: center;">
    	<img src="/assets/Screenshot 2024-07-23 220654.png" alt="result" width="500" height="500">
</div>

It seems to be magnificient and not doable, but trust me, I'll walk you from the scratch. 

## What is Newton's method?

- Newton's method, which is also called Newton-Raphson method, is a mathematical technique to approximate roots of a function.
- The general formula of Newton's method:
 
<div style="text-align: center;">
    	<img src="/assets/Pasted image 20240716190043.png" alt="result" width="500" height="200">
</div>

- The domain of this formula is all real-valued numbers 
- The general idea of the Newton's method is to find roots of a function which is too difficult to solve, for example third- and fourth-degree polynomials or a transcendental equation such as cosx = x.
- We can extend the concept to apply to the complex numbers follow this formula:

<div style="text-align: center;">
    	<img src="/assets/Pasted image 20240719134818.png" alt="result" width="500" height="200">
</div>

- The only difference here is instead of using real-valued numbers, we can use complex numbers.
- So, here it comes the concept of approximation. We will use the formula above to approximate the x or x's which are satisfied the equation.
- As the formula shown, we need to find the derivative of the function f(x).
- Then the hard part is to choose an initial guess (or x<sub>n</sub>)
- Applying the formula until we get the x<sub>n+1</sub> very close to x<sub>n</sub>, which is when the initial guess converges to the roots of the equation.

You now have the general idea of the Newton's method, we should switch gear to the fractal part.

## What is a fractal?

- Fractals are complex geometric patterns that can be split into parts, each of which is a reduced-scale copy of  the whole. They exhibit a property called "self-similarity", meaning each part of the fractals looks like the whole shape, but at a smaller scale.
- We have many popular fractals can be mentioned:
  - Mandelbrot Set: A famous fractal named after mathematician Benoit Mandelbrot.
  - ![Mandelbrot Set](/assets/Mandelbrot_sequence_new.gif)
  - Koch Snowflake: Created by repeatedly adding smaller equilateral triangles to each side of a larger equilateral triangle.
  - ![Koch Snowflake](/assets/480px-Zooming_in_a_point_of_Koch_curve_that_is_not_a_vertex.gif)
  - Sierpinski Triangle: Formed by repeatedly removing smaller triangles from a larger equilateral triangle, creating a pattern of increasingly smaller triangles.
  - ![Sierpinski Triangle](/assets/Random_Sierpinski_Triangle_animation.gif)

I am sure that you have the idea of what fractals are, let's jump right into our project.

## Project overview

In this section, you will grasp the general idea of this project.

- In this project, we will use C++ to generate Newton's fractals as images (PPM format) which will be written into disk.
- For any complex function (function that accepts input as complex numbers) the Newton's method will estimate the complex roots of f(Z<sub>n</sub>) = 0 using the formula we see above.
- We have to choose initial guess Z<sub>0</sub>, which is difficult so I'll not mention in this blog, then use the mentioned technique to improve it until it converges to a root of the equation.
- To determine the shade of each pixel that corresponds to the initial Z<sub>0</sub>, we need to set it based on the number of iteration it takes to converge or not converge.
- We will use this function: f(Z<sub>n</sub>) = Z<sub>n</sub><sup>3</sup>  - 2Z<sub>n</sub> + 2 --> f'(Z<sub>n</sub>) = 3Z<sub>n</sub><sup>2</sup> - 2
