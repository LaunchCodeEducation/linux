---
title: "Commands"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 110
---

## `nginx` CLI Command: `reload`

The `nginx.service` is controlled with the `systemctl` tool, which is the preferred way of working with the running service. However, when an NGINX configuration file is altered `systemctl` has no way of instructing the service to reload the configuration.

The `nginx` CLI provides a command that allows you to reload the process, including any changed configuration files, this command is `sudo nginx -s reload`.

{{% notice green "Bonus" "rocket" %}}
In total there are four signals you can send using the `nginx` CLI:
- `nginx -s stop`
- `nginx -s quit`
- `nginx -s reopen`
- `nginx -s reload`

This course only requires you to understand `reload`.
{{% /notice %}}

**Anytime a change is made to an NGINX configuration file the process must be reloaded with `sudo nginx -s reload`**