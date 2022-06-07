---
title: "Slides"
date: 2022-03-22T10:37:21-05:00
draft: false
hidden: true
# type: "slides"
weight: 100
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## Web Servers

---

## Purpose

Program that allows you to serve web pages to the end user
___

### Protocols

HTTP: Hypertext Transfer Protocol

HTTPS: Hypertext Transfer Protocol Secure

---

## Web Servers Covered

Caddy: Serve files and reverse proxy, automatic HTTPS

Nginx: Serve files and reverse proxy, no automatic HTTPS

Both of the above web servers can accomplish the same tasks
___

### Use Cases

This course utilizes Caddy and NGINX to server static files as web applications for the following:

- React Project
- Spring Boot Project
- Angular Project
- C# Project
- Python Project

Caddy - User friendly, less configuration, newer technology (released in 2015)

NGINX - Many organizations still use Nginx (released in 2004)

This Linux Course curriculum is currently being served with a Caddyfile

---

## Caddy

Requires a Caddyfile to be configured in order to serve web applications

default Caddyfile located at /etc/caddy/Caddyfile

Best practice is to store your Caddyfile in the default location

---

## NGINX

Requires a .conf (config) file to be configured in order to server web applications

default .conf file located at /etc/nginx/conf.d/default.conf

Best practice to store any custom .conf files at /etc/nginx/conf.d/

{{< /slides >}}