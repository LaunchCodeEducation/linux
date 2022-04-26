---
title: "React Exercise"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 100
---

## Deploy Artifacts (GitHub)

You can find the artifacts for this project at the [React Tic Tac Toe Tutorial artifacts GitHub repo](https://github.com/LaunchCodeTechnicalTraining/react-tic-tac-toe-build-artifacts)

## Instructions

1. Configure NGINX to serve the files that make up the `react-tic-tac-toe-build-artifacts` project

## Questions & Answers

### What did the NGINX configuration need to contain to properly serve the artifacts?

{{% expand "CLICK FOR ANSWER" %}}
```nginx
server {
    listen 80;
    server_name localhost;

    location / {
        root /home/student/react-tic-tac-toe-build-artifacts;
        index index.html;
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
