---
title: "Reverse Proxy"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 120
---

```
http {
    server {
        location / {
            proxy_pass http://localhost:8080/;
        }
    }
}
```