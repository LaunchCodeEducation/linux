---
title: "Spring Unit File"
date: 2021-03-16T15:12:13-06:00
draft: false
weight: 140
---

- clone repo
- build artifact
- create unit file pointing at artifact

{{% notice note %}}
this is a best practice, but you would want a more powerful webserver to reverse proxy to the running internal tomcat server. we will see an example of this soon.
{{% /notice %}}

A common way `systemd` is used with regards to web development is to harden the deployment of a web app.

`Caddy` and `NGINX` come pre-configured as services that will restart when failed. 

However, if we are using one of these web servers to reverse proxy to our own application server we are responsible for ensuring our application server is hardened. This can be done easily using `systemd`. We can simply define a unit-file for our application, configure it to restart on failure, configure it to start on machine reboot. This will make our application available even if the applciation framework crashes (maybe because it ran out of RAM), or if the machine powers down and back up (maybe because a power outage happened).

This article will walk us through creating a service out of a Spring application.