---
layout: post
title:      "JavaScript"
date:       2020-03-02 21:58:17 +0000
permalink:  javascript
---


While I thoroughly enjoyed learning Ruby, from building basic CLI programs through Sinatra and Rails applications, JavaScript seemed slightly more intriguing to me me, mostly because it is similar syntactically to languages I was already somewhat familiar with. Over the past two weeks I have been reviewing JS fundamentals, however, I have also learned quite a lot thus far.

One of the more eye-opening aspects of JS which I have recently been practicing is AJAX (Asynchronous JavaScript and XML). AJAX allows us to make get, post, put, patch and delete requests. While I have come to understand that there are a wide variety of strategies for making these requests, the `fetch` method makes handling requests fairly simple.

> fetch(SOME_URL + SOME_ROUTE)
>     .then(response => response.json())
>     .then(obj => console.log(obj));

> fetch(SOME_URL + SOME_ROUTE, {
>     method: "POST",
>     headers: {
>         "Content-Type": "application/json",
>         "Accept": "application/json"
>     },
>     body: JSON.stringify({
>         someObject
>     })
> })
> .then(response => response.json())
> .then(obj => console.log(obj));

Above are two examples of an AJAX get and post request respectively. While the concept of promises isn't entirely solidified in my mind, I believe that the first call to `then` is awaiting a response from the provided URL and the second call is awaiting an object to be constructed from the promise returned by the `fetch` method although this is just a presumption. From the other examples of AJAX which I have stumbled across, this seems to be the most simplified and readable approach.

Another aspect of JS which I've been getting accustomed to is how functions behave. In the other languages I'm familiar with callbacks are generally passed as function signatures (delegates) which require specified parameters. JavaScript, however, treats functions as first-class citizens which allows them to be handled far more easily.

I'm currently looking forward to starting my JS and Rails project, and although I haven't decided on what my project will be, I have quite a few ideas. Until then I look forward to learning much more about JavaScript.
