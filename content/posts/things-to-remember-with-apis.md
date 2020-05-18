---
title: "Things to Remember With Apis"
date: 2020-05-18T14:39:02-04:00
draft: false
---

While working with API's I always find myself getting bitten by the same things so now I will keep a list of things to
remember. Most of these things get taken care when using a framework but when you're building from
scratch (for whatever reason, let's not fight over our choices)  it's easy to forget.

This list **is not extensive**, will keep updating it as I remember (or happens again at work) or feel free to contact me with what you have experienced, I will gladly add it (and give you credit).


1. [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) If the client is running in a browser and in a different domain from the API everything will be broken
2. [IP Forwarding](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Forwarded-For) Imagine we require to know the IP of the user. Assuming they will make a request directly to our 
backend server is rare these days assuming you're running in cloud or behind any kind of load balancer or reverse proxy. Make sure to test in production :wink:
3. Timeout configuration: This will vary depending on what is used by each application, generally means databases and other apis that get consumed. Always set the connection and transfer timeout.
