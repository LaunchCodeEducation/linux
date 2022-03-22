---
title: "Install"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 100
originalAuthor: Paul Matthews # to be set by page creator
originalAuthorGitHub: pdmxdd # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

https://nginx.org/en/linux_packages.html

works for `focal`

https://nginx.org/en/linux_packages.html#Ubuntu

Install Tools Used in Installation:
```
sudo apt install curl gnupg2 ca-certificates lsb-release ubuntu-keyring
```

Download and add the nginx_signing.key:
```
curl https://nginx.org/keys/nginx_signing.key | gpg --dearmor \
    | sudo tee /usr/share/keyrings/nginx-archive-keyring.gpg >/dev/null
```

Check the contents of the nginx_signing.key:
```
gpg --dry-run --quiet --import --import-options import-show /usr/share/keyrings/nginx-archive-keyring.gpg
```

Desired Output of the nginx_signing.key:
```
pub   rsa2048 2011-08-19 [SC] [expires: 2024-06-14]
      573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62
uid                      nginx signing key <signing-key@nginx.com>
```

Add package repo:
```
echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
http://nginx.org/packages/ubuntu `lsb_release -cs` nginx" \
    | sudo tee /etc/apt/sources.list.d/nginx.list
```

Set up repository pinning to prefer our packages over distribution-provided ones:
```
echo -e "Package: *\nPin: origin nginx.org\nPin: release o=nginx\nPin-Priority: 900\n" \
    | sudo tee /etc/apt/preferences.d/99nginx
```

Update Package Repository List and then install nginx from repo:
```
sudo apt update
sudo apt install nginx
```