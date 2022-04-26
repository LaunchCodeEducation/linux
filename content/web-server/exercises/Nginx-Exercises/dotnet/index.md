---
title: ".NET Exercise"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 110
---

## Dependencies

{{% include "web-server/exercises/dotnet_installation.md" %}}

## Deploy Artifacts (GitHub)

You can find the artifacts for this project at the [.NET Techjobs MVC artifacts GitHub repo](https://github.com/LaunchCodeTechnicalTraining/dotnet-techjobs-mvc-artifacts).

## Instructions

Using the project dependencies and the deploy artifacts:

1. start the application server
1. configure NGINX to serve as a reverse proxy to the running application server

### Hints

#### Starting the Application Server

1. Figure out how to start a .NET application with the `dotnet` CLI.
1. Figure out how to start a .NET application with the **executable** script in the Project artifact directory.

#### NGINX Troubleshooting

1. NGINX and Caddy can't both be running as they conflict over the ports `80` and `443`.
1. Use the `systemctl` stop and start commands to ensure only NGINX is active.

## Questions & Answers

### How can the application server be started with the `dotnet` CLI?

{{% expand "CLICK FOR ANSWER" %}}

```bash
cd dotnet-techjobs-mvc-artifacts
dotnet TechJobsMVC.dll
```

Optionally you can invoke the script found in the artifact directory `./TechJobsMVC` after changing into the project directory.
{{% /expand %}}

### What port was the application server running on?

{{% expand "CLICK FOR ANSWER" %}}
The Kestrel server was running on: `http://localhost:5000`. Port `5000`.

![dotnet TechJobs.dll output](pictures/dotnet-port.png?classes=border)

Take note of the output in the picture where it mentions listening on `http://localhost:5000`.

{{% /expand %}}

### What did the NGINX configuration need to contain to serve as a reverse proxy?

{{% expand "CLICK FOR ANSWER" %}}
```nginx
server {
    listen 80;
    server_name localhost;

    location / {
        proxy_pass http://localhost:5000;
    }
}
```
{{% /expand %}}

### What command was used to reload NGINX after a change was made to the configuration file?

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo nginx -s reload
```
{{% /expand %}}