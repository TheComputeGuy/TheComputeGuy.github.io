---
title: "TIL: Python Try-Except-Else, For/While-Else and Exception notes and groups"
date: 2025-02-15T10:04:10-07:00
description: "The ubiquitous try-except-else and loop-else pattern in Python. Bonus addendum on exception notes and groups."
tags: ["TIL", "Python"]
math: false
---

Just last week, I was going through an extremely comprehensive Python codebase, whose main author is someone who has amazing knowledge of Python minutiae, and I found a couple of new 'patterns' which I had not seen before, at least in my brief software dev experience across JS, Java and C/C++. 

## Try-Except-*Else*

The first one was
```python
try:
    do_something()
except SomeException as e:
    logger.exception(f"Exception logging message: {e}")
else:
    do_something_else_after()
```

An `else` after a try?

Documentation - [https://docs.python.org/3/tutorial/errors.html#:~:text=The%20try%20%E2%80%A6,%E2%80%A6%20except%20statement.](https://docs.python.org/3/tutorial/errors.html#:~:text=The%20try%20%E2%80%A6,%E2%80%A6%20except%20statement.)

This is a very smart code pattern - now, if you want to execute something after your code that is in a `try` block if your primary source of exception code doesn't raise an exception, to maintain control flow, you'll usually want to write it after your do_something() within the try block itself, especially if you aren't raising an exception in the `except` block (basically if do_something_else_after() should run if do_something() does not raise, but not run if there's an exception). So instead of putting your do_something_else_after() in the `try` block itself, and polluting the scope of the `except` block, you should put it in the `else` right after all the except blocks. Smart move!

Note - if you have a `finally` block in this set, it runs _after_ your `else` block.

---

## Loop-*Else*

The second interesting code pattern I found was:

```python
for x in range(p):
    do_something()
    .
    .
    .
    if some_condition:
        break
else:
    do_something_else()
```
or
```python
while p:
    do_something()
    .
    .
    .
    if some_condition:
        break
else:
    do_something_else()
```
An `else` after a loop?!

Documentation - [https://docs.python.org/3/tutorial/controlflow.html#else-clauses-on-loops](https://docs.python.org/3/tutorial/controlflow.html#else-clauses-on-loops)

This is another ubiquitous but smart code pattern, which is useful to run code when the loop doesn't `break` (or `return` or `raise`). If you want to run a certain piece of code only when the loop fully executes but doesn't break out of the control flow out-of-order, use an `else` block. Although the else is for the for/while loop in the example, it **CAN** be thought of as an else for the if condition (CAN be THOUGHT OF, but isn't in reality). The else block is executed after the for/while loop ends.

---

## Bonus: Exception Notes and Exception Groups

Bonus TIL I learnt when reading docs in detail for this article: Exception Notes and Exception Groups

Documentation - [https://docs.python.org/3/tutorial/errors.html#enriching-exceptions-with-notes](https://docs.python.org/3/tutorial/errors.html#enriching-exceptions-with-notes)

Basically, if you want to add additional context to your exceptions, especially about the runtime conditions at the point where this exception was raised, you can do that using exception notes. Copying the example over from the documentation:

```python
try:
    raise TypeError('bad type')
except Exception as e:
    e.add_note('Add some information')
    e.add_note('Add some more information')
    raise
...
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
    raise TypeError('bad type')
TypeError: bad type
Add some information
Add some more information
```

So at this point, if this was running as a part of a thread, I could add the thread ID, or if it was a loop, I can add the iteration or retry count in case of an exponential backoff, or an execution ID or a request ID, anything that can be useful for investigating based on logs later.
What I do currently is that I push these details as a part of the exception message itself, which might or might not be the best idea - still debating that.

An exception group is just a convenience mechanism to group together a lot of exceptions and raise them at once - maybe you want to monitor your exceptions but don't want to break the control flow necessarily - you can catch and collect them (along with additional info as notes^) and then raise them all at once.

---

These are handy control flow mechanisms, adding tiny bits of convenience for Python programmers.