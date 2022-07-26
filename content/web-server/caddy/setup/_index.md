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
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo gpg --dearmor -o /usr/share/keyrings/caddy-stable-archive-keyring.gpg
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
sudo systemctl start caddy
```

Check status:

![systemctl-status-caddy](pictures/systemctl-status-caddy.png?classes=border)

```bash
systemctl status caddy
```

### Curl Localhost

![curl-localhost-caddy](pictures/curl-localhost-caddy.png?classes=border)

If you scroll towards the top of the STDOUT you will find similar html formatting.

```bash
curl localhost
```

### Caddy Stop

![caddy-stop](pictures/caddy-stop.png?classes=border)

```bash
caddy stop
```

```bash
curl localhost
```

![caddy-stop-curl](pictures/caddy-stop-curl.png?classes=border)

