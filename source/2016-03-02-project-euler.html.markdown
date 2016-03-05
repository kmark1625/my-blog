---
title: Lessons Learned Solving Problems 1-25 on Project Euler
date: 2016-03-02
tags: project euler
---

I set out with the goal of solving as many problems of Project Euler as I could in 3 months. Below is a set of lessons that I learned along the way from each set of problems. I decided to approach the problems sequentially and would not move on from a given set until all problems in that set were completed. I had to learn about numerous topics in coding and mathematics in order to complete the challenge. I hope this article will be helpful for a reader who is seeking to attempt a similar challenge for themselves or just a reader who is curious what the journey is like.

## Problems 1-25

## Math

There are some fundamental mathematical concepts that are required in order to solve the first set of problems. Prime numbers and factors occur over and over again throughout the first set of problems. Other math concepts that come up are usually explained in enough detail in the problem statement to get by.

### Prime Numbers

Prime numbers occur over and over again throughout the first set of problems. It is essential to know both how to efficiently generate a list of prime numbers as well as determine if a given number is prime. A prime is a number that is only divisible by one and itself. You can make optimizations to your prime checker by only iterating through 2 to the square root of the number. In some problems, it is useful to cache a sorted list of primes that you can then check to see if the number is in the list.

### Factors

Determining factors of a number is essential. Two common ideas that come up are greatest common factor and least common factor. It will be useful to be able to calculate these two quantities and to make use of them.

## Programming

There are some fundamental programming concepts that are helpful to solving the first set of problems.

### Test Driven Development

I found test driven development to be essential in order to determine if an answer was correct. Many of the questions often ask for extreme numbers for their problems, but they generally give a simple case when explaining them. Often, you can use that simple case to base a test suite on. Then, you can ensure that you pass the simple case before attempting to generalize or extend your solution. I found coding this way greatly decreased the time spent debugging at the end.

### Itertools and Generator Functions

I used python exclusively to solve the first set of problems. I found itertools invaluable for permutations and combintations. In addition, generator functions were essential to quickly calculate values on the fly without having to generate and entire list of all values.

### Object-Oriented Approach

I found some problems lent themselves to solving with an object-oriented approach. For example, there was a problem that required use of dates. I found it was easy for me to write this method with an object oriented approach as it was much easier to test each part of the code.