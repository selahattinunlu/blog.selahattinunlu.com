---
title: How to wait for a container to be ready?
date: 2019/08/04 19:00:00
description: "How to wait for a container to be ready"
tags:
    - docker
---

### The Problem

First of first, I don't have much experiences on Docker. I'm just trying to dockerize one of my side-project and I thought can learn about Docker. Although I did not deploy it yet, it seems great to use it in development at least. Anyway, let's talk about the main subject.

If you've worked with Docker before, you know that some containers might depends to the others. For example, your backend applications might depends to the MongoDB (just like in my case). In this case, backend application must wait until the mongo container is runned. 

There are a couple of ways to set that dependencies in your configuration files. `depends_on` is one of them and I was using it in my application. Everything were working perfectly at the beginning but today I've encountered with a problem! My application was not connnecting to the MongoDB. But how? It was working last week and I did not do anything! What the hack?

Then, I've checked the logs and realized that the MongoDB was being ready to wait connections after my backend application is runned! But I had used `depends_on` configuration! I've done a quick google search and understood the problem. 

--- 

**depends_on** only cares about if the container is runned or not. So, does not matter whether mongodb is ready for connections. Aha! It's so sensible. How could docker knows if it's ready or not?

---

### The Solution

I've searched the solution as well and found a couple of solutions. I'm gonna tell you the best one for me.

The solution is **wait-for-it.sh** [Here is the repository](https://github.com/vishnubob/wait-for-it)

It's a bash script to wait on the availability of a TCP host and port. You can find that description at it's repository 'It is useful for synchronizing the spin-up of interdependent services, such as linked docker containers.'

#### How to apply the solution

- I've copied `wait-for-it.sh` file into my app folder.

- Then add those lines into Dockerfile:

```bash
COPY wait-for-it.sh /usr/wait-for-it.sh
RUN chmod +x /usr/wait-for-it.sh
```

- And the final step, I've changed application command in docker-compose.yml:

```bash
app:
    container_name: backend
    restart: always
    build: .
    volumes:
        - .:/usr/src/app
        - /usr/src/app/node_modules
    ports:
        - "3030:3030"
        - "9229:9229"
    depends_on:
        - mongo
    command: bash -c "/usr/wait-for-it.sh --timeout=0 mongo:27017 && npm run dev"
```

That's all! My backend application waits until mongodb is ready for connections. End of the story! :)

