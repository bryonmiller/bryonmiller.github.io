---
title: "Recursive JavaScript: Fibonacci"
slug: "recursive-javascript-fibonacci"
post_id: "2186"
type: "post"
status: "publish"
date: "2015-07-25 15:56:59"
modified: "2015-07-25 15:56:59"
author: "bmreverb"
original_url: "https://bryonmiller.com/blog/recursive-javascript-fibonacci/"
categories: ["Uncategorised"]
tags: ["coding", "fibonacci", "JavaScript", "recursion"]
---

I have been struggling through the idea of recursion this week, particularly when it comes to the code for the Fibonacci sequence. I'm not sure why this baffled me (the iterative version took me a minute to grasp, but nothing like this), but it really had me confused last night. After a few articles last night, writing things out on a piece of paper, and one phenomenal YouTube video...**I GOT IT!** I want to share some info about it with you as well.
[caption id="attachment\_50" align="alignnone" width="300"][![Recursive Fibonacci](http://blog.bryonmiller.com/wp-content/uploads/2015/07/IMG_0803-2-300x225.jpg)](http://blog.bryonmiller.com/wp-content/uploads/2015/07/IMG_0803-2.jpg) Working out the Fibonacci function via recursion by hand.[/caption]

## What is Recursion

If you aren't familiar with recursion, it is essentially a using a function to call on itself a necessary number of times in an effort to solve a problem. Wikipedia defines it as such:
> **Recursion** in [computer science](https://en.wikipedia.org/wiki/Computer_science "Computer science") is a method where the solution to a problem depends on solutions to smaller instances of the same problem (as opposed to [iteration](https://en.wikipedia.org/wiki/Iteration#Computing "Iteration")).[[1]](https://en.wikipedia.org/wiki/Recursion_(computer_science)#cite_note-1) The approach can be applied to many types of problems, and [recursion](https://en.wikipedia.org/wiki/Recursion "Recursion") is one of the central ideas of computer science.[[2]](https://en.wikipedia.org/wiki/Recursion_(computer_science)#cite_note-2)

(Here is that article: [Recursion (computer science)](https://en.wikipedia.org/wiki/Recursion_(computer_science) "Recursion (Computer Science)").) It is a very useful skill, although it really isn't necessary to work our the Fibonacci sequence. For more information on how this can be used to find a number in the Fibonacci sequence, as well as the resources I used to grasp it, keep reading. Let's dig in!

## The Resources I Used

Here are some links to help you if you are also struggling with this topic.

- [Wikipedia Article on the Fibonnaci Sequence](https://en.wikipedia.org/wiki/Fibonacci_number "Fibonacci Sequence - Wikipedia")
  - This gives you the basics and the math behind the sequence. It also gives you the formula (Fn = F(n-1) + F(n-2)) that you will need for the recursive version.
- If you haven't read Eloquent JavaScript ([read it free *here*](http://eloquentjavascript.net/ "Eloquent JavaScript")), you are missing out. For the section of the chapter on functions that covers recursion, *[click here](http://eloquentjavascript.net/03_functions.html#h_jxl1p970Fy "Eloquent JavaScript - Chapter 3 - Recursion")*.
  - This book is an excellent resource for anyone wanting to learn JavaScript. This section is what got me started thinking about recursion.
- Finally, check out this video: ["Recursion - Fibonacci Numbers (JavaScript)"](https://www.youtube.com/watch?v=HIObTXnznNc "Recursive - Fibonacci Numbers")

That video (and writing it out myself on paper) is what really made it click for me.

## Conclusion

Nothing beats the satisfaction of finally solving a problem and understanding the solution. I'm sharing my code below, but I encourage you to try and work it out on your own first. Then, check against someone else's code. Good luck!
[spoiler title='My Code' style='default' collapse\_link='true']
`function fib(n) {`
`if (n === 1) {`
`return 0;`
`}`
`if (n === 2) {`
`return 1;`
`}`
`return fib(n-1) + fib(n-2)`
`}`
`console.log(fib(6));`[/spoiler]

...and here is a link to the Gist on GitHub: [RecursiveFibonacci.html](https://gist.github.com/bryonmiller/e27389f230f257992fe1#file-recursivefibonacci-html "Recursive Fibonacci - GitHub Gist"). Enjoy!
Bryon
