---
title: "Caddyfile"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 105
---

{{% notice warning %}}
This article assumes that `Caddy` is installed, and running in the background. The `Caddy service` can be started using the following command:
```bash
caddy start
```
{{% /notice %}}

## Caddyfile Configuration

{{% notice note %}}
You can view the response made by making a web request to localhost in your browser, or with curl:
```bash
curl localhost
```
This was covered in the previous article.
{{% /notice %}}

- site block
- directive
  - respond
  - root
  - file_server
  - reverse_proxy