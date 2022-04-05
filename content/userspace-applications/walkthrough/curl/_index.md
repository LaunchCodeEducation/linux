---
title: "curl"
date: 2021-03-22
draft: false
weight: 105
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "" # to be set by the page reviewer
reviewerGitHub: "" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---
## Name

> curl - transfer a URL

## Purpose

To craft HTTP(s) requests and receive HTTP(s) responses allowing you to transfer data to or from a server.

## Usage

```bash
curl [url]
```

Make and receive web requests.

Great for debugging and troubleshooting web application servers and APIs.

## Example

Make a curl request to `google.com` receiving an HTML object as a response.

```bash
curl google.com
```

Result:
![curl-google.com](pictures/curl-google.com.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
You will notice that the request page `google.com` has been moved. You can add the `-L` or `--location` option to redo the request on a new place. Try `curl -L google.com`
{{% /notice %}}

{{% notice note %}}
By default curl will automatically send a HTTP GET request. To send other types of requests you will need to add the -X option.
{{% /notice %}}

## Activity

Using the java-todo-api you will run the following curl requests:

- creating a GET request with JSON attached
 ```bash
 curl localhost:8080/todos -H Content-Type:application/json
 ```
- creating a POST request with JSON attached
```bash
curl -X POST localhost:8080/todos -H Content-Type:application/json -d '{"text":"the first task"}'
```
- creating a PUT request with JSON attached
```bash
curl -X POST localhost:8080/todos -H Content-Type:application/json -d '{"text":"the first task"}'
```
- creating a PATCH request with JSON attached
```bash
curl -X POST localhost:8080/todos -H Content-Type:application/json -d '{"text":"the first task"}'
```bash
- creating a DELETE request no JSON necessary
```bash
curl -X POST localhost:8080/todos -H Content-Type:application/json -d '{"text":"the first task"}'
```

### Necessary Options

- `-X [HTTP METHOD]`
- `-H 'content-type`: application/json': anytime we are sending a JSON request body
- `-d '{"text": "dishes"}'`: the JSON request body