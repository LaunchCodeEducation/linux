---
title: "Service: Spring Todo MVC"
weight: 100
date: 2022-04-28
---

## Setup

### Dependencies

{{% notice note %}}
This Spring Todo MVC application requires `openjdk-11-jre` to run. You should already have this on your machine. If you do not, feel free to install it with `apt`.
{{% /notice %}}

### Deploy Artifacts (GitHub)

You can find the artifacts for this project at the [Spring Todo MVC artifacts GitHub repo](https://github.com/LaunchCodeTechnicalTraining/spring-todo-mvc-artifact)

## Instructions

Using the project dependencies and the deploy artifacts **create a unit file** for the Spring Todo MVC application, **configure the unit to restart on failure**, and to **start on boot (`multi-user.target`)**.

### Create Unit File

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo touch /etc/systemd/system/todo-mvc.service
```
{{% /expand %}}

### `[Unit]` Section

{{% expand "CLICK FOR ANSWER" %}}

Using your editor of choice append the following text into the unit file.

```systemd
[Unit]
Description=Todo MVC Application
```
{{% /expand %}}

### `[Service]` Section

{{% expand "CLICK FOR ANSWER" %}}

Using your editor of choice append the following text into the unit file.

```systemd
[Service]
ExecStart=/usr/bin/java -jar /home/student/spring-todo-mvc-artifact/todo-mvc.jar
Restart=on-failure
```
{{% /expand %}}

### `[Install]` Section

{{% expand "CLICK FOR ANSWER" %}}

Using your editor of choice append the following text into the unit file.

```systemd
[Install]
WantedBy=multi-user.target
```
{{% /expand %}}

### Enable the Service

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo systemctl enable todo-mvc.service
```
{{% /expand %}}

### Start the Service

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo systemctl start todo-mvc.service
```
{{% /expand %}}

## Hints

The Spring Todo MVC application is configured to start on port `8080`, make sure no other applications are using the port.