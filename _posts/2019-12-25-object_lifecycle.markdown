---
layout: post
title:      "Object Lifecycle"
date:       2019-12-26 00:20:23 +0000
permalink:  object_lifecycle
---


The lifecycle of an object is something I originally became aware of when I began learning how to develop software a little over a year ago. Initially, the concept of variable scope, constructors and destructors is challenging, however it makes a ton of sense once you understand how to use objects effectively.

The idea of constructors and scope all seemed to sink in relatively quickly, although destructors proved to be a little more difficult for me to wrap my head around.

When I first encountered destructors, I was confused as to what the purpose of them was. At first I thought that a desctructor was a function which you would call on an object to deallocate the memory which that object was occupying. It took me hours of testing and reading into it to discover that I had it all wrong. In reality, the purpose of the destructor was to perform some code, typically closing unmanaged resources, before the object was destroyed. In my case, learning C#, the deallocation of memory was dynamically handled by the CLR (Common Language Runtime). This was without a doubt the most difficult concept for me to grasp, largely because I was already somewhat familiar with deallocating memory manually in C++.

As I continue to learn other languages and frameworks, these concepts remain consistent. Understanding these fundamentals has been invaluable, and I would encourage all aspiring developers to study these concepts in depth.
