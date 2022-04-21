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

{{% notice note %}}
The `Caddyfile` can be stored in any location as long as your path is pointing to the correct build artifacts for the application you would like to deploy. When running the command `caddy reload` you must be in the directory containing the `Caddyfile` you want to load.
{{% /notice %}}

### Create New `Caddyfile`

```bash
touch /home/student/Desktop/Caddyfile
```

Validation:

![caddyfile-desktop](pictures/caddyfile-desktop.png?classes=border)

### Add Configuration to `Caddyfile`

Using your preferred editor add the following configuration to the newly created `Caddyfile`:

```caddy
http://localhost:2018 {
    root * /home/student/Desktop/orbit-report
    file_server
}
```

Configuration breakdown:

- `http://localhost:2018`: designated port to listen on
  - `root * /home/student/Desktop/orbit-report`: Path to build directory
  - `file_server`: static file server directive

### Clone Build Artifacts

The `Caddyfile` is expecting `/home/student/Desktop/orbit-report` to contain the artifacts (HTML, CSS, JS, media files), as of now the directory doesn't exist and the build artifacts are missing.

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

Validation:

![ls-orbit-report](pictures/ls-orbit-report.png?classes=border)

```bash
ls /home/student/Desktop/orbit-report/
```

### Reload Configuration

```bash
cd ~/Desktop
```

```bash
caddy reload
```

### Access Site

Make a web request to localhost:2018.

![localhost-2018](pictures/localhost-2018.png?classes=border)