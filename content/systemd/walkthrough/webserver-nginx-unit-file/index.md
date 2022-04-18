---
title: "Webserver: Nginx Unit File"
date: 2021-03-16T15:12:13-06:00
draft: false
weight: 130
---

view the status of the NGINX service

where is it's unit file?

```bash
systemctl status nginx
```

```bash
Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset:>
```

```bash
cat /lib/systemd/system/nginx.service
```

```bash
[Unit]
Description=nginx - high performance web server
Documentation=https://nginx.org/en/docs
After=network-online.target remote-fs.target nss-lookup.target
Wants=network-online.target

[Service]
Type=forking
PIDFile=/var/run/nginx.pid
ExecStart=/usr/sbin/nginx -c /etc/nginx/nginx.conf
ExecReload=/bin/sh -c "/bin/kill -s HUP $(/bin/cat /var/run/nginx.pid)"
ExecStop=/bin/sh -c "/bin/kill -s TERM $(/bin/cat /var/run/nginx.pid)"

[Install]
WantedBy=multi-user.target
```