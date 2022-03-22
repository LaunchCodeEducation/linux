---
title: "nginx.conf"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 105
originalAuthor: Paul Matthews # to be set by page creator
originalAuthorGitHub: pdmxdd # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

conf location:

- `/usr/local/nginx/conf`
- `/etc/nginx`
- `/usr/local/etc/nginx`

- `http`
- `server`
- directive
  - `listen`
  - `location`
    - `root` /absolute/path/to/dir
    - `proxy_pass` http://localhost:8080;