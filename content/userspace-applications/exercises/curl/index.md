---
title: "Curl Exercises"
date: 2021-11-09T15:12:20-06:00
draft: false
weight: 105
---

## Questions & Answers

### What is the purpose of curl?

{{% expand "CLICK FOR ANSWER" %}}
To craft HTTP(s) requests and receive HTTP(s) responses allowing you to transfer data from or to a server.
{{% /expand %}}

### How do you make a `GET` request to `www.google.com`?

{{% expand "CLICK FOR ANSWER" %}}
```bash
curl www.google.com
```
{{% /expand %}}

### How do you change the HTTP request method using curl?

{{% expand "CLICK FOR ANSWER" %}}
With the `-X` option.

#### Get

```bash
curl -X GET [URL]
```

#### Post

```bash
curl -X POST [URL]
```

#### Put

```bash
curl -X PUT [URL]
```

#### Patch

```bash
curl -X PATCH [URL]
```

#### Delete

```bash
curl -X DELETE [URL]
```
{{% /expand %}}

### How do you include a request header with curl?

{{% expand "CLICK FOR ANSWER" %}}
With the `-H` option.

#### Adding a Content-Type: application/json header

```bash
curl -X POST [URL] -H 'Content-Type:application/json'
```
{{% /expand %}}

### How do you include a request body with curl?

{{% expand "CLICK FOR ANSWER" %}}
With the `-d` option.

#### Adding a JSON request body
```bash
curl -X POST [URL] -d '{"animalType": "dog", "name": "Bernie", "age": 6}'
```
{{% /expand %}}