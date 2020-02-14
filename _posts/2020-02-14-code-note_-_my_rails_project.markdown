---
layout: post
title:      "Code-Note - My Rails Project"
date:       2020-02-14 13:49:29 +0000
permalink:  code-note_-_my_rails_project
---

At this moment, I've just pushed (what I believe to be) my final commit for this project and look forward to my assessment. The process was more difficult than I anticipated in some ways, but that isn't a bad thing when you're learning or memorizing new concepts.

The first step I took after deciding what features my application would be comprised of, was to create a new rails app and figure out how to get a PostgreSQL database working. This first step involved installing PostgreSQL 12, reconfiguring my application (mainly database.yml) and about two hours of reading documentation inbetween twenty or so `rake db:setup` commands before I was able to get it up and running. During this process I also installed Node.js and Yarn due to an issue with the `javascript_pack_tag` located in application.html.erb. How much of this was necessary I'm unsure of, however, I was glad that I was able to tackle each problem as it presented itself and work my way toward a solution.

Once I had a working database, I made great progress. Each of my models, their relationships and basic validations, as well as routes, controller actions and simple views were up in no time. It wasn't until I decided to implement OmniAuth that I stumbled into a bit of a roadblock. Originally my `User` model only had two properties, `username` and `password`. It wasn't long before I realized that using `User.find_by(username: request.env["omniauth.auth"]["info"]["name"])` was going to be a problem. Essentially this would allow a user with a GitHub nickname which matches the username of another user to sign in as that user. After some slight rumination I decided to add an `email` property to users and use `User.find_by(email: request.env["omniauth.auth"]["info"]["email"])`. Then I ran into a new problem, where `@user` is `nil` within my view. After a small debugging session I realized that my email needed to be public on GitHub and then all was well. Of course, this solution isn't foolproof, but unless I were to have each user verify their email address when they create an account there's always going to be a flaw.

I had some trouble deciding on how I would incorporate a scope method, mostly because activerecord provides so many useful queries out of the box. I eventually decided that I didn't care for the verbosity of queries such as `@user.languages.find(language).posts`, and built a scope method, `find_by_language` for `Post`. The former query can now be written as `@user.posts.find_by_language(language)`, which not only helped me to reduce the amount of code in my posts controller, but is also significantly easier to read.

CSS is finally beginning to click. I noticed that I was able to consistently achieve the result I was expecting and this attempt at it turned out much better than my last. I have thoroughly enjoyed working with Ruby and I look forward to getting acquainted with JavaScript in the ensuing weeks.
