---
title: "Slides: Fullscreen"
date: 2022-03-22T10:37:21-05:00
draft: false
hidden: true
type: "slides"
weight: 105
---

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

Caddy - User friendly, less configuration, newer technology (released in 2015)

Nginx - Many organizations still use Nginx (released in 2004)

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