---
title: ".NET Exercise"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 110
---

## Dependencies

{{% include "web-server/exercises/dotnet_installation.md" %}}

## Clone React Build Artifacts:

Clone the following repository to the home directory:

```bash
git clone https://github.com/LaunchCodeTechnicalTraining/dotnet-techjobs-mvc-artifacts
```

How do you deploy the `dotnet-techjobs-mvc` project using Caddy?

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

Start the .NET application:

```bash
dotnet run
```

Create a `Caddyfile`

 - You can create the `Caddyfile` anywhere you would like. For this exercise it was created inside of the home directory.

Add the following code to the `Caddyfile`

```caddy
## Default localhost port
https://localhost {
        reverse_proxy http://localhost:5000
}
```

Reload the Caddy Service:

```bash
caddy reload
```

![Reload Caddy Service](pictures/caddy-reload.png?classes=border)

Open Localhost in the browser:

![Open http://localhost in browser](pictures/dotnet-localhost.png?classes=border)
{{% /expand %}}