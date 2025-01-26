---
title: URI - Warm up Contest to OBI 2016 - first phase
author: Marianne Linhares
header-img: img/sky2.jpg
date: 2016-06-13
tags: [Post]
layout: article
category: pre_2017
---

# URI - Warm up Contest to OBI 2016 - first phase

Hey there, Recently happened the [Warm up Contest to OBI 2016](https://youtu.be/PjAmKjxww9k) and I was one of the authors, it was a nice experience! I wrote 3 problems: [Prant and the Indecision](https://www.urionlinejudge.com.br/judge/pt/problems/view/2064), [Odd, Even or Cheating](https://www.urionlinejudge.com.br/judge/pt/problems/view/2059) e [Setting up a Date](https://www.urionlinejudge.com.br/judge/pt/problems/view/2068). The Portuguese editorial is [in this link](https://www.urionlinejudge.com.br/hosted/editorial/aquecimento-obi-2016-fase-1.html). Soon may be an English editorial :)!

Since, for now, an English editorial is not available, I'll make a fast
editorial for my problems, hope this helps!

## Odd, Even or Cheating

> _By: Marianne Linhares_

In this problem the rules of the game must be well understood and correctly implemented. There are only 2 possibilities of result, player 1 wins or player 2 wins, a draw is not possible. The possible cases of player 1 to win are:

  * The numbers chosen doesn't matter, player 1 cheats and player 2 doesn't accuse player 1
  * The numbers chosen doesn't matter, player 1 doesn't cheat and player 2 accuses player 1
  * Player 1 chooses even, player 1 doesn't cheat, player 2 doesn't accuse player 1 and the sum of the chosen numbers is even
  * Player 1 chooses odd, player 1 doesn't cheat, player 2 doesn't accuse player 1 and the sum of the chosen numbers is odd
If none of these cases happen then player 2 wins.
  * **Complexity**: constant.

## Setting up a Date

> _By: Marianne Linhares_

This problem can be solved using Geometric Probability. We can define the possible arrival times of Mel and Tob as points in the cartesian coordinate system, each possible time is a (x, y) inside the square determined by (0, 0) and (t2-t1, t2-t1) that represents the possible meeting interval. We also have the maximum wait time N as a constant that will determine the possible area of meeting. This whole situation can be represented below.

![l.png](https://www.urionlinejudge.com.br/hosted/editorial/l.png)  

So, the probability of happening a meet is defined by A1/AT. To get the irreductible fraction just divide each term by gcd(A1, AT).

  * **Complexity**: basically constant.

## Prant and the Indecision

> _By: Marianne Linhares_

The problem can be easily understood through the sample. But summarizing the
problem situation: given a string of size *m* and *n* *changing letters
operations* (1 ≤ m, n ≤ 100 000), such that a *changing letter operation*
consists of changing all letters *a* to *b* (where *a* and *b* can be any
letter in the alphabet) and all letters *b* to *a* in the current word,
you should make a program that determines which word contains more favorite
letters given the order of the operations.

The difficulty of the problem is how to obtain such word in an efficient
way, a solution that simulates the changes directly would be O(m * n)
and this is not fast enough. A possible solution is instead of updating the
entire word at each change just update the letters involved in the change.

This can be done through an array that relates each letter to some other
(in other words, it holds the current status of the changes), besides another
array that holds how many times each letter appears in the word.
Bellow there is an example of how a change could be simulated following the
described implementation, where *ch* is the array that holds the "relations"
and value holds the number of occurrences of each letter in the current word:

    scanf(" %c %c", &c1, &c2);

    for(int j = 0; j < 26; j++) {
        if(ch[j] == c1) pos_c1 = j;
        if(ch[j] == c2) pos_c2 = j;
    }

    aux = ch[pos_c1]; ch[pos_c1] = ch[pos_c2]; ch[pos_c2] = aux;
    aux = value[c1 - 'a']; value[c1 - 'a'] = value[c2 - 'a']; value[c2 - 'a'] = aux;


After updating these arrays you should verify if the sum of the occurrences of
the favorite letters (you can get this information trough the value array in
O(26) is the greatest until now, if this happens just copy the ch array into
another so in the end you can print the word.

* **Complexity**: O(26 * n)
* **Complexity using a map**: O(26 * n * log(26)

> PS: Another way to implement this is using a map. The solution will be more
intuitive but a little less efficient(an irrelevant constant will be added).
