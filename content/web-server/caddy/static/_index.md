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

## New Configuration File

A common practice is to have a `Caddyfile` in your working directory with the proper configurations to load.

Below you will find the steps to create new `Caddyfile` for the Angular Orbit Report

### Create New `Caddyfile` File

```bash
touch /home/student/Caddyfile
```

Validation:

![touch-caddyfile](pictures/touch-caddyfile.png?classes=border)

### Add Configuration to `orbit-report.conf`

Add the following configuration to `orbit-report.conf`:

```nginx
server {
    listen 80;
    server_name localhost;

    location / {
        root /home/student/website/orbit-report;
        index index.html;
    }
}
```

Configuration breakdown:

- `server`: defining a new server in NGINX
- `listen`: the port the server is listening on (standard HTTP 80)
- `server_name`: the domain name, or IP address of the server (`localhost`)
- `location /`: URL path location directive, dictates how HTTP requests to the `/` (root) are handled
  - `root`: the location of the files to be served at the configured path
  - `index`: the filename for any non-provided file paths (attached automatically by NGINX, never seen by the web user)

{{% notice note %}}
If you reload the `nginx` configuration file and make a request to localhost you would see a 404 Not Found error, because currently the directory `/home/student/website/orbit-report/` does not have an `index.html` file.
{{% /notice %}}

### Clone Build Artifacts

NGINX is expecting `/home/student/website/orbit-report/` to contain the artifacts (HTML, CSS, JS, media files), as of now the directory doesn't exist and the build artifacts are missing.

Luckily the build artifacts are stored on GitHub.

From your home directory:

```bash
git clone https://github.com/LaunchCodeTechnicalTraining/orbit-report-artifacts
```

From here we will want to move the contents of `orbit-report-artifacts` into `/home/student/website/orbit-report/`.

### Move Build Artifacts to `/home/student/website/orbit-report`

Create `/home/student/website/orbit-report`

```bash
mkdir -p /home/student/website/orbit-report
```

{{% notice green "Bonus" "rocket" %}}
The `-p` flag instructs the `mkdir` command to make any necessary parent directories in the path provided. In this case it's likely that both `website/` and `/website/orbit-report` are being created!
{{% /notice %}}

Move all files in `/home/student/orbit-report-artifacts/` into `/home/student/website/orbit-report`:

```bash
mv /home/student/orbit-report-artifacts/* /home/student/website/orbit-report/
```

Validation:

![ls /home/student/website/orbit-report output](pictures/ls-orbit-report.png?classes=border)

### Reload Configuration

```bash
sudo nginx -s reload
```

### Access Site

Make a web request to localhost.

![orbit-report in browser picture](pictures/orbit-report-in-browser.png?classes=border)

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