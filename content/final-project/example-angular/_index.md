---
title: "Example: Angular Initialization Script"
weight: 100
date: 2022-05-05
---

<!-- TODO: switch to orbit report durh -->

## Get Organized

What needed to happen for the Angular project to be deployed?

### VirtualBox

1. VirtualBox Image created
1. VirtualBox First time setup completed

### Machine State

1. `git` must be installed
1. web server must be installed I'll use `caddy`

### Project Artifacts

The artifacts are already built, I just need to install them onto the machine with `git`.

1. use `git` to clone build artifacts

### Web Server Configuration

`caddy` must be configured to catch HTTP requests and respond as a `file_server`, and then must be reloaded.

1. configure `caddy`
1. reload `caddy`

At this point the `angular` project should be accessible.

## The Script

### Organization

```bash
# Install Dependencies (Machine State)

# Download Project Artifacts

# Configure Web Server
```

### Install Dependencies

```bash
# Install Dependencies

## Update Package Repositories
sudo apt update -y

## Install Git
sudo apt install git

## Install Caddy

### Add Caddy Package
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list

### Update Package Repositories

sudo apt update -y

### Install Caddy
sudo apt install caddy
```

### Download Project Artifacts

```bash
# Download Project Artifacts
git clone https://github.com/LaunchCodeTechnicalTraining/angular-tour-of-heroes-artifacts
```

### Configure Web Server

This is a little different, we have to create a valid `Caddyfile` that instructs it to catch HTTP requests and serve the files in our build artifact directory. We could manually do this with `vim` or Visual Studio Code or something, or we could use a `bash` Heredoc to create a file.

```bash
# Configure Web Server

## Create Caddyfile
(
cat <<'EOF'
https://localhost {
    root * /home/student/angular-tour-of-heroes-artifacts/
    file_server
}
EOF
) > Caddyfile

## Reload Caddy
sudo caddy reload
```

## Full Script Solution

```bash
#!/bin/bash

# Install Dependencies

## Update Package Repositories
sudo apt update -y

## Install Git
sudo apt install git

## Install Caddy

### Add Caddy Package
sudo apt install -y debian-keyring debian-archive-keyring apt-transport-https
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' | sudo tee /etc/apt/trusted.gpg.d/caddy-stable.asc
curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' | sudo tee /etc/apt/sources.list.d/caddy-stable.list

### Update Package Repositories

sudo apt update -y

### Install Caddy
sudo apt install caddy

# Download Project Artifacts
git clone https://github.com/LaunchCodeTechnicalTraining/angular-tour-of-heroes-artifacts

# Configure Web Server

## Create Caddyfile
(
cat <<'EOF'
https://localhost {
    root * /home/student/angular-tour-of-heroes-artifacts/
    file_server
}
EOF
) > Caddyfile

## Reload Caddy
sudo caddy reload
```

## Validation

### New VirtualBox Image

I deleted my old virtual box images to emphasize the point that this script will do all the work of configuring the machine.

{{% notice warning %}}
I would recommend **creating a new virtual machine instead of deleting** and starting fresh.
{{% /notice %}}

After deleting all virtual machines with a fresh virtual box home screen:

![Picture of VirtualBox home screen after removing all virtual machines](pictures/no-virtualmachines.png?classes=border)

### First time VirtualBox Setup

Booting the machine after inserting the virtual `CD` boot disk:

![alt-text](pictures/first-time-setup.png?classes=border)

Still installing:

![alt-text](pictures/installation-underway.png?classes=border)

Still installing:

![alt-text](pictures/still-going.png?classes=border)

First time login:

![alt-text](pictures/first-login.png?classes=border)

### Run Script

Write and view script:

![alt-text](pictures/cat-script.png?classes=border)

Run script:

![alt-text](pictures/run-script-one.png?classes=border)

![alt-text](pictures/run-script-two.png?classes=border)

![alt-text](pictures/run-script-three.png?classes=border)

![alt-text](pictures/run-script-done.png?classes=border)

### Check Browser