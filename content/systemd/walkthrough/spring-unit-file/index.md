---
title: "Spring Unit File"
date: 2021-03-16T15:12:13-06:00
draft: false
weight: 140
---

A common way `systemd` is used with regards to web development is to strengthen the deployment of a web app.

`Caddy` and `NGINX` come pre-configured as services that will restart when failed. 

However, if you are using one of these web servers to reverse proxy to your own application server you are also responsible for ensuring the application server will restart when failed. You are also responsible for ensuring the application server will start if the computer itself crashes and reboots.

This can be done easily using `systemd`. You can define a unit-file for your application, configure it to restart on failure, configure it to start on machine reboot. This will make the application available even if the application framework crashes (maybe because it ran out of RAM), or if the machine powers down and back up (maybe because a power outage happened).

This article will walk through creating a service out of a Spring application.

## Setup

You will be running the `spring-techjobs-mvc` application that was deployed in the NGINX Reverse Proxy article. You may already have the artifact you will need on your computer, check in your home directory for a directory named `spring-techjobs-mvc-artifact/`.

### Clone If Necessary

If you do not have the artifact you will need to clone the repository that contains the artifact:

```bash
git clone https://github.com/LaunchCodeTechnicalTraining/spring-techjobs-mvc-artifact
```

### Install JRE 11 If Necessary

If you do not already have the OpenJDK-11 JRE installed on your computer you can install it with:

```bash
sudo apt update -y
sudo apt install openjdk-11-jre
```

## Write Unit File

Create a file named `techjobs-mvc.service` in `/etc/systemd/system/`:

```bash
sudo touch /etc/systemd/system/techjobs-mvc.service
```

Add the following contents to the file:

```systemd
[Unit]
Description=TechJobs MVC LaunchCode Style!

[Service]
ExecStart=/usr/bin/java -jar /home/student/spring-techjobs-mvc-artifact/spring-mvc.jar
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

## Start Unit

```bash
systemctl status techjobs-mvc
```

```bash
sudo systemctl start techjobs-mvc
```

After starting the unit the application should be available in your browser at port `8080`.

![TechJobs MVC Running in Browser at localhost:8080](pictures/techjobs-in-browser.png?classes=border)

{{% notice warning %}}
If your application did not start it is likely port `8080` is currently being used. You can stop whatever process is running on that port in multiple ways. The easiest would be to `reboot` the virtual machine. Another would be to detect the `PID` of whatever is running on port `8080` and send a SIGNAL to stop it:
```bash
sudo lsof -ti :8080
sudo kill -9 [output from previous command]
```
{{% /notice %}}

## Enable Unit

```bash
sudo systemctl enable techjobs-mvc
```

Now that systemd has been instructed to restart the service when it fails, and to automatically start the service on computer boot, the application will restart itself if it crashes for any reason, and it will begin if the server itself ever crashes! Try killing the `PID` of the service and rebooting your computer and the application will still be available.

{{% notice green "Bonus" "rocket" %}}
If you have previous configured a web server like NGINX or Caddy to reverse proxy to an application running on port `8080` and the web server is currently running you will be able to access this spring application on port `80` in addition to port `8080`. This is demonstrating how an application would be deployed on a server and made accessible through the internet!
{{% /notice %}}