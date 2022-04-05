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
By default curl will automatically send a `HTTP GET` request. To send other types of requests you will need to add the `-X [HTTP METHOD]` option.
{{% /notice %}}

## curl Options:

- `-H` or `--header`: Specifies an extra header to include in any HTTP request being sent to a server. You can specify any amount of extra headers.
- `-X [HTTP METHOD]` or `--request [HTTP METHOD]`: specify what type of HTTP request you want to send to the server.
- `-s` or `--silent`: Silent mode. When added to a curl request you will not see a progress meter or any error messages.
- `-d` or `data <data>`: Sends specific data in a POST request to the HTTP server. 

## Activity

Using the java-todo-api you will practice following curl requests:

Create a GET request with JSON attached
 ```bash
 curl localhost:8080/todos -H Content-Type:application/json
 ```
Create a POST request with JSON attached
```bash
curl -X POST localhost:8080/todos -H Content-Type:application/json -d '{"text":"the first task"}'
```
<!-- - creating a PUT request with JSON attached -->
<!-- TODO: Clarity - Currently no PUT mapping on todo-api -->
Create a PATCH request with JSON attached
```bash
curl -X PATCH localhost:8080/todos/{id} -H 'Content-Type:application/json'
```

{{% notice note %}}
You will need to replace the `{id}` portion of the above curl request with an existing todo id.
{{% /notice %}}

Create a DELETE request
```bash
curl -X DELETE localhost:8080/todos/{id}
```

{{% notice note %}}
You will need to replace the `{id}` portion of the above curl request with an existing todo id.
{{% /notice %}}

### Necessary Options

- `-X [HTTP METHOD]`: This syntax designates what type of HTTP Method you are sending to the server (**GET,POST,PUT,PATCH,DELETE**)
- `-H 'content-type`: application/json': anytime you are sending a JSON request body you need to provide the header option
- `-d '{"text": "dishes"}'`: the JSON request body