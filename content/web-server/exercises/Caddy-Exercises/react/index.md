---
title: "React Exercise"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 100
---

## Install Build Dependencies:

<!-- TODO: Add Install Include Option for nvm -->

## Clone React Build Artifacts:

Clone the following repository to the home directory:

```bash
git clone https://github.com/LaunchCodeTechnicalTraining/react-tic-tac-toe-build-artifacts
```

How do you deploy the `react-tic-tac-toe` project using Caddy?

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

Create a `Caddyfile`

 - You can create the `Caddyfile` anywhere you would like. For this exercise it was created inside of the home directory.

Add the following code to the `Caddyfile`

```caddy
## Default localhost port
https://localhost {
    ## Path to build directory
    root * /home/student/react-tic-tac-toe-build-artifacts
    ## file_server directive
    file_server
}
```

Reload the Caddy Service:

```bash
caddy reload
```

![Reload Caddy Service](pictures/caddy-reload.png?classes=border)

Open Localhost in the browser:

![Open https://localhost in browser](pictures/localhost-react.png?classes=border)
{{% /expand %}}

