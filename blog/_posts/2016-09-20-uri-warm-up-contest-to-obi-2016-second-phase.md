---
title: URI - Warm up Contest to OBI 2016 -second phase
author: Marianne Linhares
header-img:
date: 2016-09-20
tags: [Post]
layout: article
category: pre_2017
---

# URI - Warm up Contest to OBI 2016 -second phase

Hey there, Not so recently happened the [Warm up Contest to OBI 2016](https://www.urionlinejudge.com.br/judge/pt/problems/origin/121) and I
was one of the authors again ([I was one of the authors in the first phase as well](https://mariannelinhares.wordpress.com/2016/06/13/uri-warm-up-contest-to-obi-2016-first-phase/))!
I wrote 1 problem: [Rio 2016](https://www.urionlinejudge.com.br/judge/pt/problems/view/2177)
and I'll make a fast editorial of this problem and, hopefully, this will help someone :)!

## Rio 2016

> _By: Marianne Linhares_

This problem is very straight forward, reading the problem carefully is easy to
see that we should calculate the distance between the points and then compare it
with the time that the match will begin.

Buuuut, be careful with the use of integers, the multiplication may not fit in
an integer, so you should use long long int (C++) for the position variables.
A C++ solution can be seen [here](https://github.com/mari-linhares/Programming/blob/master/OnlineJudges/URI/Math/2177/code.cpp).

  * **Complexity**: O(n).
