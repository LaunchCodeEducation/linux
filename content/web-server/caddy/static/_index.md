---
title: "Static Website"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 115
---

## Configuring Caddy to Serve a Static Website

A common task performed by a web server is to serve websites.

Sometimes the website to be served is a static website. A static website only requires that the HTML, CSS, JS, and media files (like .jpgs) need to be served as an HTTP Response.

The syntax for a `Caddyfile` meant to serve a static website will look similar to the following:

```caddy
localhost {
    root * /absolute/path/to/build/artifact/directory
    file_server
}
```
<!-- 127.0.0.1 {
    root * /absolute/path/to/build/artifact/directory
    file_server
}
```

additional file_server options:

```
localhost {
    root * /absolute/path/to/build/artifact/directory
    file_server {
        precompressed gzip zstd
    } 
}
```

force http:

```
http://localhost {
    root * /absolute/path/to/build/artifact/directory
    file_server
}
``` -->