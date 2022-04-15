---
title: "Install"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 100
---

https://caddyserver.com/docs/install#debian-ubuntu-raspbian

Stable Release:

```bash
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list
sudo apt update
sudo apt install caddy
```

`which caddy`

`caddy version`

`caddy help`

{{% notice note %}}
`systemctl status caddy.service`
{{% /notice %}}
