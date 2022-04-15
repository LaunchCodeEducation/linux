---
title: "curl"
date: 2021-03-22
draft: false
weight: 105
---

{{% notice note %}}
This walkthrough will utilize a Java Spring Rest API. Clone the following github url and run the .jar file within: `https://github.com/LaunchCodeTechnicalTraining/spring-todo-api-jar`
![git-clone-jar](pictures/git-clone-jar.png?classes=border)
{{% /notice %}}

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
curl www.google.com
```

Result:
![curl-google.com](pictures/curl-google.com.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
If you try to send a `GET` request to "google.com" you will receive a notification the document has been moved. If you were to run the request again with the -L option to follow the redirect of the new location you would have the correct response.
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

### Make a `GET` request with JSON attached
 ```bash
 curl localhost:8080/todos -H Content-Type:application/json
 ```

![curl-get-json](pictures/curl-get-json.png?classes=border)

### Make a `POST` request with JSON attached
```bash
curl -X POST localhost:8080/todos -H Content-Type:application/json -d '{"text":"the first task"}'
```

![curl-post-json](pictures/curl-post-json.png?classes=border)

### Make a `PATCH` request with JSON attached
```bash
curl -X PATCH localhost:8080/todos/1 -H 'Content-Type:application/json'
```

![curl-patch-json](pictures/curl-patch-json.png?classes=border)

{{% notice note %}}
You will need to replace the `{id}` portion of the above curl request which is represented with a **"1"** with an existing todo id.
{{% /notice %}}


### Validation:

You have created a new todo through a POST request and made a minor update with a PATCH request. Check your changes with another GET request:

```bash
curl localhost:8080/todos
```

![curl-validation](pictures/curl-validation.png?classes=border)

### Make a `DELETE` request
```bash
curl -X DELETE localhost:8080/todos/{id}
```

![curl-delete-request](pictures/curl-delete-request.png?classes=border)

{{% notice note %}}
You will need to replace the `{id}` portion of the above curl request which is represented with a **"1"** with an existing todo id.
{{% /notice %}}

## Recap:
- curl: tool to transfer data to or from a server.
- curl options:
  - `-H` or `--headers`: Specify headers for request
  - `-X` or `--request`: Specify what type of request you want to make
  - `-s` or `--silent`: Hide progress and error messages
  - `-d` or `--data`: Data included in POST request
- Send HTTP requests to an existing REST API
  - `GET`: Retrieve data from desired resource
  - `POST`: Submit data to desired resource
  - `PATCH`: Replace data of a desired resource
  - `DELETE`: Delete target resource