---
title: A fast introduction to Mocking with Python
author: Marianne Linhares
header-img:
date: 2017-01-17
tags: [Post, Outreachy, OpenStack]
layout: article
category: pre_2017
---

# A fast introduction to Mocking with Python

Hey there, This post goal is to talk a little about Mocking, and how to do that (hopefully well) in Python. These are the main topics of this article, have fun!

  1. Are you mocking me, what is mock?
  2. Mocking use cases
  3. How to mock in Python?
  4. References

# Are you mocking me, what is mock?

Mocking consists basically in abstracting some part of your code (function call, variable, API request, system call, …) and instead of using the real thing, just pretend that it is there and it works correctly.

Why do you want this? Mocking is mainly used for unit testing, why do we run unit tests? To be more confident that some particular and well-defined part of you code is working as it should. But what if **part A** of the code, that you’re interested in testing with unit tests, has a dependency with **complex part B**? You definitely don’t want the unit test testing the **complex part B**, **complex part B** will have its own unit tests, right? So how can we abstract **complex part B**? That’s right, Mocking it!!!

“In short, mocking is creating objects that simulate the behavior of real objects.”[2]

# Mocking use cases

 There’s a lot of valid use cases for Mocking, all of the ones I’ll say are related to unit tests because it is the mainly general use case for Mocking.

  * As I said in the last section, a good reason to mock a part of your code is in order to maintain unit tests isolated and concise. It’s not a good thing to have a unit test that tests a lot of things at once. You're probably will prefer to break this big unit test in smaller ones, and mock can offer a cool way to do it!
  * Sometimes part of the code you want to test is just not working as it should (not ready yet, unstable, for some reason not available, failing), mocking in this case, is a good thing, because you can test the already stable part of the code.
  * To actually run some part of the code can be too costly or have some side effect not desired (API requests, create files, writing in files, system calls), so mocking can really help you test the code without worrying with these.
  * Test unpredictable code, good unit tests are always executed expecting the same values, random values can be mocked to avoid randomness in the unit tests.
  * Mock a certain complex object that you don’t really need to have it entirely, you can mock only the parts that interest you in the context.
  * And many more cases...

**Important:** Mocking is very powerful, but do it “the right way” is not that simple and involves practice and experience, a lot Mocking (especially bad mocking) can actually make your unit tests less effective.

# How to mock in Python?

> Using the mock package [5].

## What can you do with the mock package?

* **Pretend to be anything you want!**

```python
import mock
anything = mock.Mock(return_value=3)
print anything() # 3
```

“Mock is a flexible mock object intended to replace the use of stubs and test
doubles throughout your code”. The Mock Class can be used to repeat basically
anything in the code, in the example above it represents a function that returns
3. Other useful things you can define for the Mock objects are:

  * _"side_effect_: A function to be called whenever the Mock is called. See the [`side_effect`](https://docs.python.org/3/library/unittest.mock.html#unittest.mock.Mock.side_effect) attribute. Useful for raising exceptions or dynamically changing return values. If _side_effect_ is an iterable then each call to the mock will return the next value from the iterable."

  * _"return_value_: The value returned when the mock is called. By default this is a new Mock (created on first access). "

  * _"name_: If the mock has a name then it will be used in the repr of the mock. This can be useful for debugging. The name is propagated to child mocks."

An alternative for Mock Class is MagicMock, "`MagicMock` is a subclass of `[Mock`](https://docs.python.org/3/library/unittest.mock.html#unittest.mock.Mock) with default implementations of most of the magic methods. You can use `MagicMock` without having to configure the magic methods yourself."

  * **Pretend to be a particular thing (object, function, call, ...)**

```python
from mock import create_autospec

def any_function(a, b, c): pass

mock_function = create_autospec(any_function, return_value='unicorn')
print mock_function(1, 2, 3) # returns 'unicorn'
mock_function.assert_called_once_with(1, 2, 3)
print mock_function('wrong arguments') # error
```

"The `[mock.create_autospec`](http://www.voidspace.org.uk/python/mock/helpers.html#autospeccing) method creates a functionally equivalent instance to the provided class. What this means, practically speaking, is that when the returned instance is interacted with, it will raise exceptions if used in illegal ways."

# References

[1] https://www.toptal.com/python/an-introduction-to-mocking-in-python

[2] http://stackoverflow.com/questions/2665812/what-is-mocking

[3] http://www.voidspace.org.uk/python/mock/mock.html

[4] https://docs.python.org/3/library/unittest.mock.html

[5] http://blog.thedigitalcatonline.com/blog/2016/03/06/python-mocks-a-gentle-introduction-part-1/#.WH9emXUrKkB
