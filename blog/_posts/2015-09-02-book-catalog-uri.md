---
title: Solution to Books Catalog/Catálogo de Livros 1802 (URI)
author: Marianne Linhares
header-img:
date: 2015-09-02
tags: [Post]
layout: article
category: pre_2017
---

# #Random Code 1 - Books Catalog/Catálogo de Livros 1802 (URI)

Hi! In this article we'll discuss the **[Books Catalog](https://www.urionlinejudge.com.br/judge/en/problems/view/1802) **from URI.

It's a nice question that's involves the following concepts: **algorithm efficiency, logic, and Brute force**.

So, talking about the problem! In summary we have different set of books, where each set defined by a subject (portuguese, math, physics, chemistry and biology). We know that each book of a certain subject has a value associated and we want to make a set composed by one book of each subject. Given a number **K** we want to know the sum of the **K** most valuable sets.

If is not clear, try to understand with the example bellow: The input is composed by 6 lines, the 5 first are defining  the values of the books of a certain subject where the first number is how many books of this subject there is (1 <= **n** <= 5). Then there is **n** numbers, (v1,v2,v3,...vi, where **i <= n** and **1 <= vi <= 1000**), these are the values of each book in the set. The next line is just **K**.  Sample:

5 2 5 6 3 8

5 9 6 3 1 5

5 4 8 5 2 6

5 3 2 4 9 5

5 7 8 5 1 4

1

In this case what is the answer? Well, **K** = 1 so we want to know the most valuable set possible. In this case a **greedy** solution works, we get the most valuable book of each subject and the sum is the answer  of the most valuable set possible. Bellow in green there are the elements we are present in the set, and the answer would be 42.

5 2 5 6 3 **8**

5 **9** 6 3 1 5

5 4 **8** 5 2 6  

5 3 2 4 **9** 5  

5 7 **8** 5 1 4  

1

8 + 9 + 8 + 9 + 8 = 41.

If **K** was equal to 2. We would be looking for the sum of the most valuable set + the second one. The second most valuable set, that is represented bellow in yellow, that sums up 41, so the answer is 42 + 41 = 83.

5 2 5 6 3 **8**

5 **9** 6 3 1 5

5 4 **8** 5 2 6  

5 3 2 4 **9** 5  

5 **7** 8 5 1 4  

1

8 + 9 + 8 + 9 + 7 = 41.

Ok, nice... But when **K** > 1 we'll have to choose some book to be removed and another one to be inserted in the set... that seems a hard choice... So, how to use this idea in a simpler way? Tip: always look at the input size.

**N** (number of books of each different set) is **<= 5**. That's a pretty small number, and we can implement a "not so efficient" solution. We also know that **K** is less than **P** * **M** * **Q** * **F** * **B**. This makes sense because we have to compose a set of (p, m, q, f, b),  p is portuguese book, m is a math book, ..., so **P** * **M** * **Q** * **F** * **B** possibilities exists.
