---
layout: post
title:      "Recoder - My Second Portfolio Project"
date:       2020-01-12 23:52:13 -0500
permalink:  table_relations
---


Before I began working on this project I was using the in-browser IDE. I have had Visual Studio Code for quite some time and finally decided to install Git and Ruby on my local machine for this project. After a few hours of struggling to get things working properly I realized how beneficial it is to have a local repository for projects like these. I no longer needed to worry about losing connection or logging in to learn.co to be productive, and in the long run, it has saved me a lot of time.

For my project I decided to build a web application which allows a user to view and create posts which are comprised of a code snippet and a description. I have been learning multiple languages over the past two years and figured it would be great to have a place to view small chunks of code written in various languages and frameworks to remind me of the syntax as I continue to learn.

I was initially concerned with this project after seeing examples from other Flatiron students. CSS is something that I have worked with sparingly in the past and it seemed as though these particular students had a pretty good grasp of it. As I write this, I am nearing the end of my project and have learned a lot, I now feel at least somewhat comfortable writing CSS, and although my layout doesn't look great, I'm happy with how it turned out and look forward to learning more about CSS in my spare time.

The first thing I decided to do with this project (aside from creating the essential scafolding, Gemfile, Rakefile, config/environment.rb etc.) was to create my models and their subsequent tables. I started by building the user model, knowing that each user needed a secure password, each user would have many posts, and I wanted to use a slug to represent their username within each route. This meant building the instance method #slug and the class method .find_by_slug(string). I then proceeded to build the post model which simply belongs to a user. Finally I created the table migrations ensuring that users had a password_digest and posts had a user_id.

Buidling RESTful routes was something I was somewhat familiar with prior to this course. I had taken a certification course on C# and we studied building RESTful routes within an ASP.NET MVC application. However, we did not actually apply our knowledge and build the application. Now that I have a good grasp on how to build these routes in a Sinatra application, I will likely attempt to build an ASP.NET application when I have some free time.

All in all, I found working on this project to be a very smooth process. I did have to stop a few times and do some research on CSS rules to get things looking the way I wanted them to, but otherwise I was unhindered from start to finish. I had a lot of fun building this application and look forward to learning much more during my time here at Flatiron.
