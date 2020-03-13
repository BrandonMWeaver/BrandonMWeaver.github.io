---
layout: post
title:      "JavaScript/Rails Project"
date:       2020-03-13 12:55:09 -0400
permalink:  javascript_rails_project
---


Over the past four months I have learned quite a lot. Now that I've had some experience building relatively simple applications, I decided that I should step out of my comfort zone and try to tackle something a little more challenging. For my project I decided to build a game using JavaScript for the front end and Rails to persist data for the game such as players and scores. While I have had minimal experience working on games using the Unity engine, I knew I was going to have a good amount of research to do. Luckily, I was able to find a good source of information for building a simple game using JavaScript and an HTML canvas element.

Many of the challenges I encountered during this process were somewhat familiar to me, and the solutions were generally similar. However, when it came time to rotate an image on the screen, I quickly realized that the canvas does not handle *everything* in a way that I immediately recognized. What I learned is that for each image which the canvas needed to render at an angle, in my case 180 degrees, you must save the current state of the canvas, set the angle of the canvas itself, then have the canvas draw and render the image and restore the canvas to its previous state. It makes a fair amount of sense, it just isn't something which I've ever had to concern myself with in the past.

Another challenge which forced me to learn something new was removing elements from an array during iteration. The reason I needed to figure this out was because I have multiple arrays which track a number of elements on the screen, and at some point during the course of a game, these elements become either 'destroyed' or move outside of the canvas view never to be seen again. While I could have just timed everything and then called `shift()` on the array (which, initially I did), I knew there was a better way to do this. What I learned is that you need to step backwards through the array.

```
for (let i = array.length - 1; i >= 0; i--) {
    if (condition) {
        array.splice(i, 1);
    }
}
```

Here, since the iterator is being decremented, we no longer have the problem of an out of bounds exception because the size of the array changed after the initialization of the loop. Now everything is efficiently removed as soon as it is no longer needed.

The back end went together without a hitch, although, at the moment I'm still not completely finished with my project. I feel very comfortable working with Rails, and using Rails as an API seems to be reasonably simple.

As of now I'm faced with a bit more testing, and a considerable amount refactoring due to unforseen challenges, but I feel that it won't take more than a few hours of focus and determination to get everything squared away. I look forward to my assessment, and I'm certain I will learn a lot more before the end of my time with this particular project.

