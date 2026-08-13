---
title: "Quora Question: Python code correction"
slug: "quora-question-python"
post_id: "65"
type: "post"
status: "publish"
date: "2015-08-04 21:37:05"
modified: "2015-08-04 21:37:05"
author: "bmreverb"
original_url: "https://bryonmiller.com/blog/quora-question-python/"
categories: ["Uncategorised"]
tags: ["coding", "python", "quora"]
---

If you aren’t using Quora, you should be. It is a great community of helpful people. Lately, I have been corresponding with another Quora member who is learning to code. He is learning Python and really doing well. I may share some more of our conversations at a later date, but today I just want to share the one we had yesterday. It was about a some code he had written that wasn’t working the way he wanted.

## The Problem Code

Here is his code.

```
from sys import argv

script, letter_file = argv

string_let='abcdefghijklmnopqrstuvwxyz'
list_of_letters = list(string_let)

f = open(letter_file)
output = f.read()

wf = open(letter_file, 'w')

def write_func():
    for j in range(26):
        for i in list_of_letters:
            wf.write(i)

write_func()
wf.close()

raw_input('Press to read contents of %r' % letter_file)

print output
```

His goal was to write every letter from a string to a file. Then, open/read that file and print the contents. He was getting it to write the contents (although it was writing it 26 times), but when he would try to print the file, it would print a blank line. After a little debugging, and cleaning up the code a bit, I was able to fix the issue. Can you tell what is wrong here?

## The Correction and Solution

Here is the corrected code that I sent him back.
[spoiler title='My Code' style='default' collapse\_link='true']

```
from sys import argv

script, letter_file = argv

string_let='abcdefghijklmnopqrstuvwxyz'
list_of_letters = list(string_let)

f = open(letter_file)

wf = open(letter_file, 'w')

def write_func():
    for i in list_of_letters:
        wf.write(i)

write_func()
wf.close()

raw_input('Press  to read contents of %r' % letter_file)

output = f.read()

print output

raw_input('Staying open...')
```

[/spoiler]
Remember, with this code we are printing the variable 'output' to the terminal. We defined 'output' as 'f.read()'. The issue occurs because of *when* it was defined in the original. What is in the file when you call the '.read()' function in the original code? Nothing at all. Therefore, output = "" and will show this when printed.
As I said, the issue was all about *when* output was assigned a value. When we move the assignment to a point where the file has been written and closed, the new contents of the file are assigned to outputs. Then, when we print it, we get the results we want. The fix is easy is that easy. Move the definition of 'output' to a point in the code after the content has been written to the file and the file is closed. Tada!

## What's Going on Here and Why?

Assigning values that can change can be tricky. We have something like the following scenario:

```
y = 1

x = y

def change_x(n):
    x = n
    return x

y = 2

change_x(y)

print x
```

What happens here can be very confusing to anyone new to programming. Notice that throughout the code, x = y. The magic happens when we reassign y and give it the value of '2'. If we were to print x immediately after 'y = 2', what would print? (Hint: The answer isn't '2'.) Even though the value of y changes, the value of x does not until we run the change\_x (y) function.
Doesn't seem right, but it is. For more information on this weird happening, read this: [Mutable and Immutable Types](http://anh.cs.luc.edu/python/hands-on/3.1/handsonHtml/graphics.html#more-on-mutable-and-immutable-types). For more information on plain old assignment, read this: [Variables and Assignment](http://anh.cs.luc.edu/python/hands-on/3.1/handsonHtml/variables.html).
Play around with these concepts and you'll get the hang of it pretty quick. Happy coding!
Bryon
