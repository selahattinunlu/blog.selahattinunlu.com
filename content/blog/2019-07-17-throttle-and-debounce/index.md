---
title: Throttle and Debounce
date: "2019-07-17T00:00:00.284Z"
description: ""
---

I think they are so cool techniques to prevent running a callback too many times.
There is a little difference between them and it was confuse me before to thinking on it.

When I started to think on it (it's today because I needed to use them), it started to seem easy to know
what I need to use.

First, we need to decide what we want to do. 

If we want to make **limitation** on a function which we runned
everytime after an event, we can use throttle. We can use throttle to decrease call number.
Let's imagine you're running a function when the mouse is moved. So, everytime you'll run the function.
You might want to limit it with 2 seconds. The method will be runned only every 2 seconds while mouse is moving.
You limited it and decreased to call size.

If we want to **defer** a function call until an event is done, we need to use **debouncing**.
There is a quick example for it. Let's image you want to make a search box that it will give the suggest
to the user according to typed text. Will you make a query in your database when user hit to the keyboard everytime? Of course, no! Because it'll hurt your database, right? You need to defer making query until the user stopped to typing.
You can say, make a query when if user does not type anything in 500ms. It's **debouncing**.

---

**Throttle** will run every **X** time.

**Debounce** will run only once when an event is done.

---

There is also great demo to fully demostrate how they work.

You can check it out: <a href="http://demo.nimius.net/debounce_throttle" target="_blank">Throttle - Debounce Demo</a>


