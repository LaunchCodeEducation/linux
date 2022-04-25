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
The `caddy` CLI offers many commands for managing and even configuring the Caddy web server. Almost all of these commands fall outside the scope of this class. We predominately interested in reloading the Caddy webserver when changes have been made to a `Caddyfile`.

To learn more about the `caddy` CLI checkout it's help page:
```bash
caddy help
```
{{% /notice %}}

{{% notice warning %}}
**Anytime a change is made to a `Caddyfile` the process must be reloaded with `caddy reload`.**
{{% /notice %}}
