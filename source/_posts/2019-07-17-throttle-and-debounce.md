---
title: Throttle and Debounce
date: 2019/07/17
description: "Throttle and Debounce"
---

I think they are so cool techniques to prevent running a function too many times.
There is a little difference between them and it was confuse me before to thinking on it.

When I started to think about it (it was today, because I needed to use them), it started to seem easy to know
what I need to use.

First, we need to decide what we want to do. 

If we want to make **limitation** on a function which runs every time when an event occurred,
we can use the throttle. We can use the throttle to decrease the number of calls.
Let's imagine you're running a function when the mouse is moved. So, everytime the function will run.
You might want to limit it to run every 2 seconds. The function will run only every 2 seconds while mouse is moving.
You limited it and decreased the number of calls.

If we want to **defer** a function call until an event is completed, we need to use **debouncing**.
There is a quick example for it. Let's imagine you want to make a search box that will give the suggestions according to text to the user. Will you make a query in your database when the user hit to the keyboard every time? Of course, no! Because it'll hurt your database, right? You need to defer making query until the user stopped to typing.
You can say, make a query when if the user won't type anything in  500ms. It's **debouncing**.

---

**Throttle** will run after every **X** time.

**Debounce** will run only once when an event is done.

---

There is also a great demo to fully demonstrate how they work.

You can check it out: <a href="http://demo.nimius.net/debounce_throttle" target="_blank">Throttle - Debounce Demo</a>


