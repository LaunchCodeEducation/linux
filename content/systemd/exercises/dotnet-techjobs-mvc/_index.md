---
title: "Service: .NET TechJobs MVC"
weight: 105
date: 2022-04-28
draft: true
---

## Setup

### Dependencies

{{% include "web-server/exercises/dotnet_installation.md" %}}

### Deploy Artifacts (GitHub)


## Instructions

Using the project dependencies and the deploy artifacts **create a unit file** for the .NET Techjobs MVC application, **configure the unit to restart on failure**, and to **start on boot (`multi-user.target`)**.

### Create Unit File

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo touch /etc/systemd/system/dotnet-techjobs-mvc.service
```
{{% /expand %}}

### `[Unit]` Section

{{% expand "CLICK FOR ANSWER" %}}

Using your editor of choice append the following text into the unit file.

```systemd
[Unit]
Description=.NET Techjobs MVC Application
```
{{% /expand %}}

### `[Service]` Section

{{% expand "CLICK FOR ANSWER" %}}

Using your editor of choice append the following text into the unit file.

```systemd
[Service]
ExecStart=
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
sudo systemctl enable dotnet-techjobs-mvc.service
```
{{% /expand %}}

### Start the Service

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo systemctl start dotnet-techjobs-mvc.service
```
{{% /expand %}}

## Hints

The .NET Techjobs MVC application is configured to start on port `5000`, make sure no other applications are using the port.