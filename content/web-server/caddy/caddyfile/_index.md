---
title: "Caddyfile"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 105
---

## Caddyfile Configuration

Caddy can be configured in multiple ways. The preferred way is by creating and managing a configuration file named `Caddyfile`.

## View Default Config File

The default `Caddyfile` file that comes with the initial Caddy installation can be located at `/etc/caddy/Caddyfile`. Take a look at the file with:

```bash
cat /etc/caddy/Caddyfile
```

Contents of `/etc/caddy/Caddyfile`

```caddy
# The Caddyfile is an easy way to configure your Caddy web server.
#
# Unless the file starts with a global options block, the first
# uncommented line is always the address of your site.
#
# To use your own domain name (with automatic HTTPS), first make
# sure your domain's A/AAAA DNS records are properly pointed to
# this machine's public IP, then replace ":80" below with your
# domain name.

:80 {
	# Set this path to your site's directory.
	root * /usr/share/caddy

	# Enable the static file server.
	file_server

	# Another common task is to set up a reverse proxy:
	# reverse_proxy localhost:8080

	# Or serve a PHP site through php-fpm:
	# php_fastcgi localhost:9000
}

# Refer to the Caddy docs for more information:
# https://caddyserver.com/docs/caddyfile
```

Lots of lines within this file are commented out notes. This default `Caddyfile` is meant to serve as an example to guide the configuration needs of the user.

Ignoring the commented out lines the file contents are:

```caddy
:80 {
  root * /usr/share/caddy
  file_server
}
```

This particular configuartion file is:
- Listening on port `80` (the default HTTP port)
- Using the path `/usr/share/caddy` for the site directory
- Enabling the static file server with the `file_server` directive

This specific configuraiton is stating that all requests made to port `80` are requesting files at the directory `/usr/share/caddy/`. Whatever files live in that directory will be matched up with any `HTTP` requests that hit this web server on port `80`.

{{% notice note %}}
In the following articles you will edit and create new Caddyfiles for a static website and reverse proxy
{{% /notice %}}