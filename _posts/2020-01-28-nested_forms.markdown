---
layout: post
title:      "Nested Forms"
date:       2020-01-29 03:22:02 +0000
permalink:  nested_forms
---


In my opinion, some of the most difficult hurdles to overcome in software development are derived from the attempt to understand the complexity of the abstractions which are built by others. Nested forms have proven to be one of those hurdles.

After reading through the documentation, googling, looking through stackoverflow posts and simply getting a nested form to work the way it is expected to, I learned a lot. Now I understand that the class method `accepts_nested_attributes_for` simply adds a reader and writer to our class to set and read the attributes of a related model. Better yet, I know how to write these setter and getter methods myself. I also know that we need to permit those attributes when we instantiate an object within our controller.

Despite reading through bits and pieces of the documentation in an attempt to understand how these forms are generated, and how the attributes are stored within `params`, I wasn't quite getting the picture. Seeing Avi break it down into basic HTML and explain each step of the process in the 'Has Many Through in Forms Lab' video review was extremely helpful, especially as a visual learner.

It's great to move past something which challenges you, especially when you gain a true understanding of the challenge along the way.
