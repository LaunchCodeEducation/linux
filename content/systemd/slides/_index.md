---
title: "Slides"
date: 2022-03-02T09:54:08-06:00
draft: false
hidden: false
# type: "slides"
weight: 100
---

{{% notice note %}}
The slides found at this location are meant to be used in personal reference. If you are reading these slides for the first time, or are presenting these slides we recommended using the Fullscreen option found below.
{{% /notice %}}

{{< slides >}}

## systemd

---

## Purpose

Responsible for initializing and managing daemons and services
___

### Interacting with systemd

Users interact with systemd by using the systemctl package and defining unit files

systemctl provides the end user access to information and control overall services, daemons, and unit files

---

## Unit Files

Unit files are used to complete a default or custom service

Each systems unit files are stored in the /lib/systemd/system directory

If you ever wish to modify the way any given unit functions you would edit the unit file inside of /etc/systemd/system
___

### Unit Files Continued

A common use for modifying a unit file would be to start or stop a service at a desired machine state (power on, power off, user login, user logout)

One major upside to this is that if your server were to ever fail, your Unit file will restart the service on reboot

{{< /slides >}}