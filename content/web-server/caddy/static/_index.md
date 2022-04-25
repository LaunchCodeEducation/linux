---
title: "Static Website"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 115
---

## Configuring Caddy to Serve a Static Website

A common task performed by a web server is to serve static websites.

A static website only requires that the HTML, CSS, JS, and media files (like .jpgs) need to be served as a part of the HTTP Response.

The syntax for a `Caddyfile` meant to serve a static website will look similar to the following:

```caddy
localhost {
    root * /absolute/path/to/build/artifact/directory
    file_server
}
```

## New Configuration File

A `Caddyfile` can technically live anywhere on the machine. Some people opt to store all of their `Caddyfiles` in `/etc/caddy`. This is similar to the best practice used by the NGINX web server.

Another practice is to store a `Caddyfile` with the source code of a project. For this example we will be deploying the `Orbit Report` angular project built in `LC101` unit 1. We will be creating a `Caddyfile` near the source code of this project.

{{% notice warning %}}
The `Caddyfile` can be stored in any location as long as your path is pointing to the correct build artifacts for the application you would like to deploy. When running the command `caddy reload` you must be in the directory containing the `Caddyfile` you want to load.
{{% /notice %}}

### Create New `Caddyfile`

```bash
touch /home/student/Desktop/Caddyfile
```

Validation:

![touch /home/student/Desktop/Caddyfile && ls /home/student/Desktop output](pictures/caddyfile-desktop.png?classes=border)

### Add Configuration to `Caddyfile`

Using your preferred editor add the following configuration to the newly created `Caddyfile`:

```caddy
http://localhost {
    root * /home/student/Desktop/orbit-report
    file_server
}
```

Configuration breakdown:

- `http://localhost`: designated hostname and port to listen on
  - `root * /home/student/Desktop/orbit-report`: the root location for all requests coming to this server
  - `file_server`: static file_server directive instructing Caddy to serve the files found in the root location as files for any incoming requests

### Clone Build Artifacts

The `Caddyfile` is expecting `/home/student/Desktop/orbit-report` to contain the artifacts (HTML, CSS, JS, media files) of this project. 

As of now the directory doesn't exist and the build artifacts are missing.

Luckily the build artifacts are stored on GitHub.

From your home directory:

```bash
git clone https://github.com/LaunchCodeTechnicalTraining/orbit-report-artifacts
```

From here you will want to move the contents of `orbit-report-artifacts` into `/home/student/Desktop/orbit-report/`.

### Move Build Artifacts to `/home/student/Desktop/orbit-report`

Create `/home/student/Desktop/orbit-report`

```bash
mkdir /home/student/Desktop/orbit-report
```

Move all files in `/home/student/orbit-report-artifacts/` into `/home/student/Desktop/orbit-report`:

```bash
mv /home/student/orbit-report-artifacts/* /home/student/Desktop/orbit-report/
```

Check the contents of `/home/student/Desktop/orbit-report`:

```bash
ls /home/student/Desktop/orbit-report/
```

Validation:

![ls /home/student/Desktop/orbit-report output](pictures/ls-orbit-report.png?classes=border)

### Reload Configuration

```bash
cd ~/Desktop
```

```bash
caddy reload
```

{{% notice warning %}}
If Caddy is not currently running you will need to start the `caddy` service with `systemctl` like:
```bash
sudo systemctl start caddy
```
{{% /notice %}}

### Access Site

Make a web request to localhost.

![localhost](pictures/localhost.png?classes=border)