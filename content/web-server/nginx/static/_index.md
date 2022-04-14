---
title: "Static Website"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 115
---

## Configuring NGINX to Serve a Static Website

A common task performed by a web server is to **serve** websites. 

Sometimes the website to be served is a static website. A static website only requires that the HTML, CSS, JS, and media files (like .jpgs) need to be served as an HTTP Response.

The default configuration of NGINX includes an example of a static website configuration.

The NGINX configuration file can be found at `/etc/nginx/conf.d/default.conf`:

```bash
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

Upon making an HTTP request to `localhost` the following HTML is returned:

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

Rendered in browser it looks like a normal webpage:

![NGINX default configuration localhost request in browser image](pictures/nginx-default-in-browser.png?classes=border)

## Editing the Existing Static Website

We can tap into the `index.html` file stored at the `root` of the default configuration file found at: `/usr/share/nginx/html` to change the file NGINX is serving.

Open `/usr/share/nginx/html/index.html` with your editor of choice.

Change the contents of `index.html` to:

```html
<!DOCTYPE html>
<html>
<head>
<title>My Site!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to my site!</h1>
<p>I am exploring how the HTML file can be changed, and NGINX will serve the changed file without skipping a beat.</p>

<p>NGINX doesn't care about the contents inside of the file's it is serving, it is simply serving the files in the manner it is instructed.</p>

<p><em>Brought to you by [YOUR NAME HERE]!</em></p>
</body>
</html>
```

{{% notice note %}}
Make sure to substitute `[YOUR NAME HERE]` with your actual name!
{{% /notice %}}

After making the changes make sure to **save** the file!

After make a new request to `localhost`.

{{% notice warning %}}
It is likely that the web browser has cached the response from NGINX. You will need to force the browser to make a new web request and not simply load from the browser's local cache. You can force the web browser to make a new web request with the hard refresh keyboard shortcut `ctrl` + `shift` + `r`.
{{% /notice %}}

Web browser output:

![NGINX altered HTML file localhost request in browser image](pictures/nginx-changed-html-in-browser.png?classes=border)

Congratulations. You changed the HTML that NGINX is configured to serve.

{{% notice note %}}
This is not the preferred way of working with NGINX. More realistically you will have already generated HTML/CSS/JS/media files that may have a complex file structure. In which case you will want to configure your own NGINX conf file.
{{% /notice %}}



```
http {
    server {
        location / {
            root /absolute/path/to/build/artifact/directory;
        }
    }
}
```