---
title: "Webserver: Nginx Unit File"
date: 2021-03-16T15:12:13-06:00
draft: false
weight: 105
---

Before viewing the NGINX unit file you need to know where the unit file lives.

## Checking Status

Check the status of the NGINX service:

```bash
systemctl status nginx
```

The output contains all of the status information about the service. The location of the unit file is recorded as a part of the `status` command:

```bash
Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset:>
```

The unit file that defines the `nginx.service` can be viewed at: `/lib/systemd/system/nginx.service`.

Print the contents of the file to `STDOUT` with `cat`:

```bash
cat /lib/systemd/system/nginx.service
```

Output:

```bash
[Unit]
Description=nginx - high performance web server
Documentation=https://nginx.org/en/docs
After=network-online.target remote-fs.target nss-lookup.target
Wants=network-online.target

[Service]
Type=forking
PIDFile=/var/run/nginx.pid
ExecStart=/usr/sbin/nginx -c /etc/nginx/nginx.conf
ExecReload=/bin/sh -c "/bin/kill -s HUP $(/bin/cat /var/run/nginx.pid)"
ExecStop=/bin/sh -c "/bin/kill -s TERM $(/bin/cat /var/run/nginx.pid)"

[Install]
WantedBy=multi-user.target
```

This course will not cover `systemd` in great depth. 

What it will cover is understanding how:
- a `unit` is defined
- to start and stop a `service` 
- to configure a `service` to start automatically on boot
- to configure a `service` to restart itself when it fails.

## [Unit]

The unit is defined by the `[Unit]` section of the unit file. 

```bash
[Unit]
Description=nginx - high performance web server
Documentation=https://nginx.org/en/docs
After=network-online.target remote-fs.target nss-lookup.target
Wants=network-online.target
```

This section contains metadata about the unit like it's **description**, and where the **documentation** can be found. 

{{% notice green "Bonus" "rocket" %}}
The `[Unit]` section also defines the relationship between this and any other units. This goes beyond the scope of this class. This explains why the **After=** and **Want=** directives are found in the `[Unit]` section of the NGINX unit file.
{{% /notice %}}

## [Service]

The `[Service]` section of the unit file provides configuration information to the `service` associated with this unit file.

```bash
[Service]
Type=forking
PIDFile=/var/run/nginx.pid
ExecStart=/usr/sbin/nginx -c /etc/nginx/nginx.conf
ExecReload=/bin/sh -c "/bin/kill -s HUP $(/bin/cat /var/run/nginx.pid)"
ExecStop=/bin/sh -c "/bin/kill -s TERM $(/bin/cat /var/run/nginx.pid)"
```

From the NGINX unit file:

- `Type=`: the type of service to be created
- `PIDFile=`: the file where the process id should be stored
- `ExecStart=`: the shell command used when the `start` command is provided
- `ExecReload=`: the shell command used when the `reload` command is provided
- `ExecStop=`: the shell command used when the `stop` command is provided

In this course we are most concerned with the `ExecStart=` directive, and will be accepting the default values for the remaining directives as we don't need to provide any additional configuration other than the default configuration for those directives.

For the `NGINX` service the `ExecStart=` directive is associated with the shell command: `/usr/sbin/nginx -c /etc/nginx/nginx.conf`.

The absolute path to the `nginx` package has been provided, this way their is **no ambiguity** on which version of `nginx` should be used to start this service.

You can view what this command does by viewing the help of the `nginx` package:

```bash
nginx -help
```

Output:

![nginx -help output](pictures/nginx-help.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
You could also execute the absolute path of the `nginx` package as it's defined in the unit file:
```bash
/usr/sbin/nginx -help
```
![/usr/sbin/nginx -help](pictures/absolute-nginx-help.png?classes=border)
{{% /notice %}}

So the `ExecStart=/usr/sbin/nginx -c /etc/nginx/nginx.conf` is simply starting the `NGINX` webserver and telling it which configuration file to use!

## [Install]

The `[Install]` section configures how the unit should behave when `enabled` or `disabled`.

```bash
[Install]
WantedBy=multi-user.target
```

From the NGINX unit file:

- `WantedBy=`: marks this unit as a dependency for the listed argument

Before the argument `multi-user.target` can be completed the service defined by this unit file must be created.

{{% notice green "Bonus" "rocket" %}}
The argument provided to the `WantedBy=` directive can be a valid unit or a computer run level. The `multi-user.target` is a run level created when a user can be prompted to login to the machine. This is the only run level we will define in this course, however many other targets may be appropriate for different applications.
{{% /notice %}}