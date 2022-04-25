---
title: "Existing Package Repositories"
weight: 100
date: 2022-04-21
---

Install each of the following packages:

- `git`
  - `sudo apt update -y`
  - `sudo apt install git`
  - `which git`
  - `git --version`
- `curl`
  - `sudo apt update -y`
  - `sudo apt install curl`
  - `which git`
  - `curl --version`
- `vim`
  - `sudo apt update -y`
  - `sudo apt install vim`
  - `which vim`
  - `vim --version`
- `openjdk-11-jdk`
  - `sudo apt update -y`
  - `sudo apt install openjdk-11-jdk`
  - `which java`
  - `java --version`

## How to update package repository list?

### Solution

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo apt update -y
```

This should be done before installing any new packages.

{{% /expand %}}


## How to install `git`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo apt install git -y
```
{{% /expand %}}



## How to install `curl`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo apt install curl -y
```
{{% /expand %}}

## How to install `vim`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo apt install vim -y
```
{{% /expand %}}

## How to install `openjdk-11-jdk`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
sudo apt install openjdk-11-jdk
```
{{% /expand %}}