---
title: "wget"
date: 2021-03-22
draft: false
weight: 100
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Name

> Wget - The non-interactive network downloader.

## Purpose

Download files over a network.

You can use it to download files over your home, school, or work network.

You can use it to download files over public networks like the internet.

{{% notice note %}}
We will only be seeing examples of downloading files over the internet.
{{% /notice %}}

## Usage

- download files in which you have a URL
  - can be any type of file:
    - Debian Package File: .deb
    - Comma Separated Values: .csv
    - Python: .py
    - Shell: .sh
    - Zipped Directory: .zip
    - Archived Directory: .tar.gz
    - Image: .png, .jpeg, .jpg
    - etc...

This site is hosting files that we can make wget requests to. We will be using the following files to practice.

{{% attachments style="blue" title="Practice Files" /%}}

By hovering over the files you can see the URL of the specific resource, in the bottom left corner of your web browser.

![hover for URL](pictures/hover-for-url.png?classes=border)

The URL has the following format: `protocol://domain/path` to future proof this curriculum we will simply provide the path to each of the files, you will be responsible for providing the protocol & domain.

## Download `hello.txt`

`wget [protocol]://[domain]/userspace-applications/walkthrough/wget/_index.files/hello.txt`

### Validation

`cat hello.txt`

## Download `hello.sh`

`wget [protocol]://[domain]/userspace-applications/walkthrough/wget/_index.files/hello.sh`

### Validation

`cat hello.sh`

`bash hello.sh`

## Download `hello.py`

`wget [protocol]://[domain]/userspace-applications/walkthrough/wget/_index.files/hello.py`

### Validation

`cat hello.py`

`python3 hello.py`

## Download `roster.csv`

`wget [protocol]://[domain]/userspace-applications/walkthrough/wget/_index.files/roster.csv`

### Validation

`cat roster.csv`

## Outside Example (Imgur)

Let's find the link for a grumpy cat photo: https://imgur.com/gallery/Xl0W2iX, open dev tools, find `src=` of the image which is: `https://i.imgur.com/Xl0W2iX.jpeg`.

Let's request that specific file with `wget`.

`wget https://i.imgur.com/Xl0W2iX.jpeg`

It downloaded a file named `Xl0W2iX.jpeg`, let's open it in Firefox and see the photo.