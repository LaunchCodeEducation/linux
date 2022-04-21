---
title: "Commands"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 110
---

## `Caddy` CLI Commands:

The Caddy service is controlled using the Caddy CLI. 

The Caddy CLI provides a command to start, stop, and reload the process. The primary reason to use the `caddy reload` command would be to recognize changes made to the `Caddyfile` configuration.

{{% notice green "Bonus" "rocket" %}}
In total there are four signals you can send using the `Caddy` CLI.
- `caddy run`: Start the service in foreground and block indefinitely
- `caddy start`: Start the service in the background
- `caddy stop`: Stop the service
- `caddy reload`: Reload caddy after making changes to config file
{{% /notice %}}

{{% notice warning %}}
Anytime a change is made to a `Caddyfile` the process must be reloaded with `caddy reload`.
{{% /notice %}}
