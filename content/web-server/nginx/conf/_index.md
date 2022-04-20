---
title: "nginx.conf"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 105
---

{{% notice warning %}}
This article assumes NGINX is installed, and the `nginx.service` is currently running. The `nginx.service` can be started by entering the following command:

```bash
systemctl start nginx
```

{{% /notice %}}


## NGINX Configuration

NGINX is predominately driven by configuration files.

To configure NGINX to server static files, or to reverse proxy to a running web application framework NGINX requires a valid configuration file that instructs the NGINX web server on how to behave.

NGINX configuration files end with the suffix `.conf`.

## Viewing Default Configuration File

By default a newly installed NGINX web server is configured to serve an example static HTML file.

{{% notice note %}}
You can view the response made by making a web request to localhost in your browser, or with curl:

```bash
curl localhost
```

This was covered in the previous article.
{{% /notice %}}

The configuration file responsible for this NGINX web server behavior is located at: `/etc/nginx/conf.d/default.conf`. Take a look at the file with:

```bash
cat /etc/nginx/conf.d/default.conf
```

Contents of `/etc/nginx/conf.d/default.conf`:

```nginx
server {
  listen      80;
  server_name localhost;

  #access_log /var/log/nginx/host.access.log  main;

  location / {
      root    /usr/share/nginx/html;
      index   index.html index.htm;
  }

  #error_page   404           /404.html;

  # redirect server error pages to the static page  /50x.html
  #
  error_page    500 502 503 504   /50x.html
  location = /50x.html {
      root    /usr/share/nginx/html;
  }

  # proxy the PHP scripts to Apache listening on 127.0.0.1:80
  #
  #location ~ \.php$ {
  #    proxy_pass    http://127.0.0.1;
  #}

  # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
  #
  #location ~ \.php$ {
  #    root            html;
  #    fastcgi_pass    127.0.0.1:9000;
  #    fastcgi_index   index.php;
  #    fastcgi_param   SCRIPT_FILENAME   /scripts$fastcgi_script_name;
  #    include         fastcgi_params;
  #}

  # deny access to .htaccess files, if Apache's document root
  # concurs with nginx's one
  #
  #location ~ /\.ht {
  #    deny    all;
  #}
}
```

There are many commented out notes in the `default.conf` file. NGINX provides this file with examples to guide the configuration  in a way that serve the needs of the user.

Ignoring the commented out lines the file contents are:

```nginx
server {
  listen      80;
  server_name localhost;

  location / {
      root    /usr/share/nginx/html;
      index   index.html index.htm;
  }

  error_page    500 502 503 504   /50x.html
  location = /50x.html {
      root    /usr/share/nginx/html;
  }
```

This configuration file: 
- is listening on port `80` (the default HTTP port)
- is named `localhost`
- any requests made to `localhost:80`: 
  - will be served from the `root` location of `/usr/share/nginx/html` (on this computer's file system)
  - if the HTTP request is missing a file extension from the path: `index.html` will be added and then `index.html` added before returning a `400 level` HTTP status code.

To NGINX this means an HTTP request made to `localhost:80/` would result in an HTTP response including the file located at `/user/share/nginx/html/index.html`.

Additional configuration instructs NGINX on handling HTTP Status Codes `500`, `502`, `503` and `504`. In the case of a `5XX` level error NGINX should respond with the corresponding `50x.html` file found in `/usr/share/nginx/html`.

{{% notice note %}}
In the following articles you will edit the existing configuration file and add new configuration files.
{{% /notice %}}

## Configuration File Location

NGINX can be configured to load `.conf` files from many different locations. It is a best practice to store any custom `.conf` in the `/etc/nginx/conf.d` directory.

## Top Level Configuration File

In addition to the user-defined configuration files there is a top level NGINX configuration file found at: `/etc/nginx/nginx.conf`.

This file contains high level configurations about NGINX itself, not for creating a new web server definition. This course will not cover the top level configuration file.

<!--

NGINX configurations are files located in a manner that NGINX expects.

```bash
systemctl status nginx

cat /lib/systemd/system/nginx.service

cat /etc/nginx/nginx.conf

ls /etc/nginx/conf.d/

cat /etc/nginx/conf.d/default.conf

```



This is what is powering the default NGINX configured website.

Looking into `/usr/share/nginx/html`:

```bash
ls /usr/share/nginx/html
```

Output:
```bash
50x.html  index.html
```

Looking at the contents of the `index.html` file:

```bash
cat /usr/share/nginx/html/index.html
```

Output:
```html
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and working. Further configuration required.</p>

<p>For online documentation and support please refer to 
<a href="http://nginx.org/">nginx.org</a>.<br />
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```

This is the exact output when we made a `curl` request to `localhost` on port 80, when running the `NGINX` server!

It's all powered by the NGINX `conf` (short for configuration files). Default 

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
-->