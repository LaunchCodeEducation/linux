---
title: "nginx.conf"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 105
---

```bash
systemctl status nginx

cat /lib/systemd/system/nginx.service

cat /etc/nginx/nginx.conf

```

conf location:

- `/usr/local/nginx/conf`
- `/etc/nginx`
- `/usr/local/etc/nginx`

- `http`
- `server`
- directive
  - `listen`
  - `location`
    - `root` /absolute/path/to/dir
    - `proxy_pass` http://localhost:8080;