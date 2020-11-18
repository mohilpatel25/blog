---
layout: post
title: Coin Change Problem using Genetic Algorithms
date: 2020-10-12 00:00:00 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: genetic-algo.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Algorithms, GeneticAlgorithms, ArtificialIntelligence] # add tag
---

Coin Change Problem using Genetic Algorithm

Genetic algorithms (GA) are algorithms that belong to the class of evolutionary algorithms, that leverage the idea of natural selection and genetics. They are generally used for generating solutions to optimization and search problems.

I tried to solve the coin change problem using Genetic Algorithm. The coin change problem is one where we want to make a change for value N using an infinite supply of coins of different denominations D={d1, d2, d3, ..., dn}. The original problem is to find the number of total ways to do so, but we will find one acceptable solution to make the change using GA.

Formulation of the problem:

- Chromosome encoding: vector C = {X1, X2, ..., Xn}, Xi denotes the number of coins of di and Xi<N.
- Fitness function: <br> <img src="https://render.githubusercontent.com/render/math?math=\large{fitness = \frac{1}{1 %2B |X1*d1 %2B X2*d2 %2B X3*d3 %2B ... %2B Xn*dn - N|}}">
- Selection: parents with the best fitness
- Crossover: one-point crossover
- Mutation: random resetting
- Survivor Selection: fitness-based

This process is repeated until we get a chromosome with fitness 1, indicating that the chromosome represents a way to make a change of N. The corresponding values in the chromosome represent the count of the denomination to be used in making the change.

Here's an example for making change of 50 with denominations of 1, 2, 3, 4, 5, 6, 7, 8.
![example]({{site.baseurl}}/assets/img/coinchangega.gif)
