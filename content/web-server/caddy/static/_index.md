---
title: "Static Website"
date: 2022-03-22T10:37:21-05:00
draft: false
weight: 115
originalAuthor: Paul Matthews # to be set by page creator
originalAuthorGitHub: pdmxdd # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

what do we mean by static?

what are the build artifacts?

- root
- file_server


```
localhost {
    root * /absolute/path/to/build/artifact/directory
    file_server
}
```

```
127.0.0.1 {
    root * /absolute/path/to/build/artifact/directory
    file_server
}
```

additional file_server options:

```
localhost {
    root * /absolute/path/to/build/artifact/directory
    file_server {
        precompressed gzip zstd
    } 
}
```

force http:

```
http://localhost {
    root * /absolute/path/to/build/artifact/directory
    file_server
}
```