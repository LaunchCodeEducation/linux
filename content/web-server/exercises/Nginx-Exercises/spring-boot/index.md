---
title: "Spring Boot Exercise"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 105
---

## Dependencies

{{% notice note %}}
This Spring Todo MVC application requires `openjdk-11-jre` to run. You should already have this on your machine. If you do not feel free to install it with `apt`.
{{% /notice %}}

## Deploy Artifacts (GitHub)

You can find the artifacts for this project at the [Spring Todo MVC artifacts GitHub repo](https://github.com/LaunchCodeTechnicalTraining/spring-todo-mvc-artifact)

## Instructions

Using the project dependencies and the deploy artifacts:

1. start the application server
1. configure NGINX to serve as a reverse proxy to the running application server

## Questions & Answers

### How can the application server be started with the `java` CLI?

{{% expand "CLICK FOR ANSWER" %}}
```bash
java -jar /home/student/spring-todo-mvc-artifact/todo-mvc.jar
```
{{% /expand %}}

### What port was the application server running on?

{{% expand "CLICK FOR ANSWER" %}}
`8080`
{{% /expand %}}

### What did the NGINX configuration need to contain to serve as a reverse proxy?

{{% expand "CLICK FOR ANSWER" %}}
```nginx
server {
    listen 80;
    server_name localhost;

    location / {
        proxy_pass http://localhost:8080;
    }
}
```
{{% /expand %}}

### What command was used to reload NGINX after a change was made to the configuration file?

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo nginx -s reload
```
{{% /expand %}}