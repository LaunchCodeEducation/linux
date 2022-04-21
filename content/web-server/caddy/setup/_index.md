---
title: "Setup"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 100
---

## Installation

<!-- https://caddyserver.com/docs/install#debian-ubuntu-raspbian -->


```bash
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
```

```bash
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
```

```bash
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
```

```bash
sudo apt update
```

```bash
sudo apt install caddy
```

## Validation

```bash
which caddy
```

```bash
caddy version
```

![which-caddy](pictures/which-caddy.png?classes=border)

Upon a successful installation you should see the location of the caddy binary and the version of the installed `caddy` package with the preceding commands.

For more information and to see useful Caddy commands run the below command:

`caddy help`

## Managing the `Caddy` Service

### Caddy Start

```bash
caddy start
```

```bash
curl localhost:2019
```

![curl-localhost-start](pictures/curl-localhost-start.png?classes=border)

### Caddy Stop

```bash
caddy stop
```

```bash
curl localhost:2019
```

![curl-localhost-stop](pictures/curl-localhost-stop.png?classes=border)

###

<!-- {{% notice note %}}
`systemctl status caddy.service`

![systemctl-status-caddy](pictures/systemctl-status-caddy.png?classes=border)
{{% /notice %}} -->
