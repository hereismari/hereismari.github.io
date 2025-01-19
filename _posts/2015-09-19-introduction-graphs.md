---
title: A graph? What is it?
author: Marianne Linhares
header-img: img/sky.jpg
date: 2015-09-19
tags: [Post]
layout: article
---

# A graph? What is it?

### Introduction

Hello, in this article we'll discuss a little bit about **graphs**. This is one
of the main topics that turns a newbie into an intermediate competitor in
programming contests (of course in my opinion).

After this article (and a bit of practice) I hope you can understand that:
* Graphs aren't in general difficult, it's just a new and more advanced concept,
  and that's why it needs previous knowledge and may take some time to get used
  to the idea.

* A lot of problems are related to graphs, almost all competitions have some
  graph problem. And when you get the idea of the classic graph algorithms,
  most problems will get simpler.

This article has the following structure:
  * Previous knowledge required
  * Graphs, a definition
  * How to represent a graph in a computational way?
  * Bibliography and suggested readings

###  Previous Knowledge Required

So, here we go! Before talking about graphs, some important topics to study are:

  1. Recursion
  2. Basic Data Structures (queue, stack, priority queue)
  3. Feel comfortable in your programming language (libraries, syntax)

If you never heard about these topics, or feel like you should know more about
them, I really suggest you take some time to study them. The major troubles
with graph implementations are due to not enough experiences in the topics
above.

### Graphs, a definition

For programming competitions the following definition is "enough" : _a graph is a data-structure, a way to organize the data, defined by a set of vertices/nodes and a set of edges that are used to connect 2 vertices._

_ _

![](http://upload.wikimedia.org/wikipedia/commons/5/57/6n-graf.png)

Graph 1

![](http://eden.dei.uc.pt/~paquete/DEI/plot2.PNG)

Graph 2

![](https://mariannelinhares.files.wordpress.com/2015/09/caeb6-jpg3.jpg)

Graph 3

Okay... but why use this model? There are many situations where a graph is a
great structural model, the most common examples are: **roads and avenues,
social networks, friend network, dependencies relations**. An example of a
problem evolving graphs is the problem **Toll** from **Brazilian Programming
Olympics(OBI) of 2002**, it says:

_John was the fist place at OBI and as a prize he and his family won a trip to
South Korea. They rented a car to get to know the country better.
The **roads(1)** are well maintained; all of them are **two-way street(2)** ,
and **two cities may be connected directly by more than one road(3)**.
But in all of them there is a **fixed value Toll(4)**. The father of John
doesn't have a lot of money to spend, so the car trips must be well planed._

Task: Write a program that, with the **cities(5) **and the **roads **in the
country, and the city where John and his family are, **find each city(don't
count the one where they already are) that can be visited, given the
restriction that the father of John wishes to pay at most P Tolls(6).**  

Ok, so it's a graph problem right? And where is the graph? Well, it's a classic example! The roads are the edges and the cities are the vertices.

![](http://www.redebrasilatual.com.br/revistas/72/cultura/copy2_of_copy_of_usa_beat.jpg)

In the problem explanation there are some interesting words and expressions that
tell us a lot to us about **how the graph is defined**. How so? Well, there are
a lot of graph classifications and types of graphs. And it will interfere in
our solution and in the graph representation.

#### **The mainly graph characteristics**  

* **Connected graph**: there is a **path** from each vertex to any other.
* **Unconnected graph**: there is one or more vertices that we can't reach
  from some other vertex.

* **Sparse graph**: if the number of edges is much less than the number of
  vertices (if is less of  the square of the number of vertices it can be
  considered  sparse).
* **Dense graph**: if the number of edges is close to the number of vertices.

* **Directed graph**: the edges have directions. In other words, if there is an
  edge from A to B (A and B are vertices) it doesn't implies in the existence of
  an edge from B to A.
* **Undirected graph**: edges have no direction. In other words, if there is an
  edge from A to B (A and B are vertices) it implies in the existence of an edge
  from B to A.

* **Weighted graph**: the edges have a weight (usually int values) associated to them.

* **Unweighted graph**: the edges doesn't have a weight associated to them.
  Other way to see it is that all edges have the same weight.
