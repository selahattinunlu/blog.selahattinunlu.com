---
title: Software Testing
date: 2019/07/21 19:00:00
description: "Software Testing"
---

I was not writing any test in any kind of project before. And then I just realized that I'm doing too many effort to test too many parts whether if they are broke or not when I changed something or add new feature into it. So, it was so painfull process for me. Worse than this is the pain will grow while project is growing. How can I save myself and my time with that bullshit? The solution is clear! I need to automate that time consuming process.

## What is the software testing?

It's a process that makes us to know if any part of code does not work up to requirements. Although it could be done also manually, we're gonna talk more about automated test. But don't forget that we can't automate everything in software and manual testing might be better choice in some cases.

## Methods

**White-Box** is related the internal logic and structure of code. Tester needs to know how works the source code.

**Black-Box** is opposite of white-box testing. Tester does not know anything about the source code and can't access it. So, tester can access only the user interface and provides input without know how they are work.

**Gray-Box** .....

## Levels

There are two main level and those are functional tests and non-functional tests. Functional test is related with code itself. We can know whether if the software works as expected or not. The non-functional tests are related with scalability, performance, security.

### Functional Tests

<p></p>

#### Unit Testing

The goal of the unit testing is isolate some part of code and correct in terms of requirements.

We test only a single function, method.

#### Integration Testing

Integration Test is tests which are performed to expose defects in integrated components (units)

The goal of the integration testing is combine parts of code and correct them together in terms of requirements.

![](https://miro.medium.com/max/300/1*xHibbXdcePT0GtpeZRgxSA.gif)


#### Functional Testing

Although unit testing and integration testing seem enough, it's not. The next level of testing is **Functional Testing**.

Also known as **e2e** tests. The goal of the functional testing is testing the application itself as a whole. In functinal tests we don't care about the internal of the application. It's like black-box tests.

This tests simulate user behavior (clicking, typing, scrolling, submitting etc.) and verify whole system is works from the point of view an end user.

---

### Non-Functional Tests

.....

---

We learned functional and non-functional test levels. The combination of functional tests and non-functional tests is **system testing**.

## Some Terms About Software Testing

### Mocks

Mocks mimic the behavior of real objects. Mocks are fake methods. In unit tests, you need to focus only one unit to test it. The other parts could be mocks.

Let's assume you're gonna test user registration and send a welcome email to the user after the user is registered. While you testing it, you might not want to send a real email. You might only want to ensure the method that will send the email is called. So in this case, you're gonna need to use **mocks**. Because when you mock email sender, it won't run it. Instead, it's gonna give you information whether it's called or not.

### Stubs

It seems like mocks. But there is further more than. In mocks, we can ensure that function is called or not. However in stubs, we can specify result we expected when the method is called.

Let's assume we have an `Auth` class and it's `guest` method gives us that user is logged in or not. In that case, if we don't care the real result, we can use stubs. We can say basically, I want to get `true` as result when `Auth's guest` method is called. After we defined it, the real `Auth` class is not gonna be runned. Instead, stub is gonna give us the result what we expected.

### Fixtures

...

### Spies

....

---

Further reading resources:

- https://medium.com/welldone-software/an-overview-of-javascript-testing-in-2019-264e19514d0a
- https://www.ijera.com/papers/Vol4_issue4/Version%209/S440999102.pdf
- https://www.softwaretestingmaterial.com/100-software-testing-interview-questions/
- https://www.edureka.co/blog/interview-questions/software-testing-interview-questions/