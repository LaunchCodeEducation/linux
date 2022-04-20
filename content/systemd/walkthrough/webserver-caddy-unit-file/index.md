---
title: "Webserver: Caddy Unit File"
date: 2021-03-16T15:12:13-06:00
draft: false
weight: 110
---

## Checking Status

```bash
systemctl status caddy
```

```bash
Loaded: loaded(/lib/systemd/system/caddy.service; enabled; vendor preset:>
```

## Viewing Unit File

```bash
cat /lib/systemd/system/caddy.service
```

```bash
# caddy.service
# For using Caddy with a config file.
#
# Make sure the ExecStart and ExecReload commands are correct
# for your installation.
#
# See https://caddyserver.com/docs/install for instructions.
# 
# WARNING: This service does not user the --resume flag, so if you
# use the API to make changes, they will be overwritten by the
# Caddyfile next time the service is restarted. If you intend to
# use Caddy's API to configure it, add the --resume flag to the 
# `caddy run` command or use the caddy-api.service file instead.

[Unit]
Description=Caddy
Documentation=https://caddyserver.com/docs
After=network.target network-online.target
Requires=network-online.target

[Service]
Type=notify
User=caddy
Group=caddy
ExecStart=/usr/bin/caddy run --environ --config /etc/caddy/Caddyfile
ExecReload=/usr/bin/caddy reload --config /etc/caddy/Caddyfile
TimeoutStopSec=5s
LimitNOFILE=1048576
LimitNPROC=512
PrivateTmp=true
ProtectSystem=full
AmbientCapabilities=CAP_NET_BIND_SERVICE

[Install]
WantedBy=multi-user.target
```

This unit file is very similar to the `NGINX` unit file.

In the `[Unit]` section it defines a description, a link to the documentation and defines some relationships.

In the `[Service]` section it sets the `ExecStart=` directive among other configurations.

In the `[Install]` section it defines that this service should be created before the `multi-user.target` run level is complete.

{{% notice green "Bonus" "rocket" %}}
Take note of how this unit file also defines the user and group this service should run under.
{{% /notice %}}