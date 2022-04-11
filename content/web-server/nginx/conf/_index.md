---
title: "nginx.conf"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 105
---

After installing, and starting the NGINX service a resource was served at localhost:80. NGINX comes pre-configured to serve the basic HTML file.

NGINX configurations are files located in a manner that NGINX expects.

```bash
systemctl status nginx

cat /lib/systemd/system/nginx.service

cat /etc/nginx/nginx.conf

ls /etc/nginx/conf.d/

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