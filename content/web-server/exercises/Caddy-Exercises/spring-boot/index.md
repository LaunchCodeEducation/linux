---
title: "Spring Boot Exercise"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 105
---

## Install Build Dependencies:

<!-- TODO: Add Install Include Option for nvm -->

## Clone React Build Artifacts:

Clone the following repository to the home directory:

```bash
git clone https://github.com/LaunchCodeTechnicalTraining/spring-todo-mvc-artifact
```

How do you deploy the `spring-todo-mvc` project using Caddy?

{{% expand "Click Here for Answer" %}}
Ensure the caddy service is running:

```bash
systemctl status caddy
```

![check caddy.service status](pictures/systemctl-status-caddy.png?classes=border)

Start the caddy service if it is inactive:

```bash
sudo systemctl start caddy
```

Start the Spring Boot project:

```bash
java -jar spring-todo-mvc-artifact/todo-mvc.jar
```

Create a `Caddyfile`

 - You can create the `Caddyfile` anywhere you would like. For this exercise it was created inside of the home directory.

Add the following code to the `Caddyfile`

```caddy
## Default localhost port
https://localhost {
    reverse_proxy http://localhost:8080
}
```

Reload the Caddy Service:

```bash
caddy reload
```

![Reload Caddy Service](pictures/caddy-reload.png?classes=border)

Open Localhost in the browser:
{{% /expand %}}