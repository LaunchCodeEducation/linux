---
title: "Wget Exercises"
date: 2021-11-09T15:12:20-06:00
draft: false
weight: 100
---

## Questions & Answers

### What is the purpose of `wget`?

{{% expand "CLICK FOR ANSWER" %}}
To download files over a network.
{{% /expand %}}

### What is the command for downloading the file found at `https://www.launchcode.org/`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
wget https://www.launchcode.org/
```
{{% /expand %}}

### What is the name of the file downloaded from `https://www.launchcode.org/`?

{{% expand "CLICK FOR ANSWER" %}}
`index.html`
{{% /expand %}}

### How could you view the contents of the file downloaded from `https://www.launchcode.org/`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
cat index.html
```
{{% /expand %}}

### Bonus: How could you tell `wget` to rename the file downloaded from `https://www.launchcode.org/` to `launchcode-homepage.html`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
wget -O launchcode-homepage.html https://www.launchcode.org/
```
{{% /expand %}}