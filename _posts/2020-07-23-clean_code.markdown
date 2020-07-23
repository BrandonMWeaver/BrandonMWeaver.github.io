---
layout: post
title:      "Clean Code"
date:       2020-07-23 18:48:56 -0400
permalink:  clean_code
---


Having recently graduated, I've spent some time learning various algorithms, a few less familiar languages and frameworks, but I've also been researching industry best practices and the importance of developing well-written, easily maintainable code.

Robert C. Martin, a software engineer and founder of the Agile Manifesto has many interesting lectures on the topic of maintainable code which can be found on [YouTube](https://www.youtube.com/c/UnityCoin). I highly recommend watching these lectures, especially if you are in the process of launching your career as a developer. In these lectures, Robert has a ton of noteworthy insights into the problems modern software companies face, and he stresses the necessity to keep code clean in order to avoid those problems.

While I have minimal experience working on software projects with other developers, a few of the projects I completed for my .NET certification training at University of Phoenix required us to develop applications as a team of four to five students. I can personally attest to how much quicker we were able to develop when I was paired with students who wrote clean, elegant code, and I can only imagine the magnitude of this difference when working with a team of tens or hundreds of developers on a large application.

Something that I have been actively practicing is writing code which, as Robert says, "allows the reader to exit early". Essentially, you want to encapsulate any logic for a function into a subset of meaningfully named functions, allowing the body of the function to declaratively express what the function does. This approach allows the person maintaining the code to invest in understanding more about the function as they move down the abstraction chain; this way they are not forced into understanding the low-level details of the function.

I believe that there is an equal, if not greater amount of practice necessary to gain the skills required to write code this way, and it's something I'm striving for more as I develop larger applications.
