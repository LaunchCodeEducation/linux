---
title: "curl"
date: 2021-03-22
draft: false
weight: 105
---

## Name

> curl - transfer a URL

## Purpose

To craft HTTP(s) requests and receive HTTP(s) responses allowing transference of data to or from a server.

## Usage

```bash
curl [url]
```

Make and receive web requests.

{{% notice green "Bonus" "rocket" %}}
Outside of making general web requests `curl` is great for debugging and troubleshooting web application servers and APIs.
{{% /notice %}}

## Example

Make a curl request to `google.com` receiving an HTML object as a response.

```bash
curl www.google.com
```

Result:
![curl-google.com](pictures/curl-google.com.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
If a `GET` request is sent to "google.com" a notification about the document being moved will be received. Running the request again with the `-L` option would instruct `curl` to follow the redirect to the new location.
{{% /notice %}}

The default HTTP method argument in `curl` is `HTTP GET` request. To send other types of requests `curl` requires the type of HTTP request method to be provided by adding the `-X [HTTP METHOD]` option.

## curl Options:

- `-H` or `--header`: Specifies an extra header to include in any HTTP request being sent to a server. You can specify any amount of extra headers.
- `-X [HTTP METHOD]` or `--request [HTTP METHOD]`: specify what type of HTTP request you want to send to the server.
- `-s` or `--silent`: Silent mode. When added to a curl request you will not see a progress meter or any error messages.
- `-d` or `data <data>`: Sends specific data in a POST request to the HTTP server.

## Setup

This article utilizes the [Java Spring Rest API](https://github.com/LaunchCodeTechnicalTraining/spring-todo-api-jar).

{{% notice warning %}}
This project includes a `.jar` file which requires the `openjdk-11-jre` package to be executed. The `openjdk-11-jre` package was installed as one of the exercises in the package manager chapter.

If you are missing this package you can install it with:

```bash
sudo apt update -y
sudo apt install openjdk-11-jre
```

Validation:

![which java && java --version output](pictures/which-java-java--version.png?classes=border)
{{% /notice %}}

### Clone Project Repository

Clone the project repository to your home directory:

```bash
git clone https://github.com/LaunchCodeTechnicalTraining/spring-todo-api-jar
```

#### Validation

Look at the home directory contents for the newly created `spring-todo-api-jar/` directory:

```bash
ls
```

Output:

![git clone https://github.com/LaunchCodeTechnicalTraining/spring-todo-api-jar && ls output](pictures/clone-validation.png?classes=border)

### Run the Application

We will be using Java Runtime Environment (`openjdk-11-jre`) to run the included `.jar` file.

Change to the project directory and run the application with:

```bash
java -jar todo-api.jar
```

Output:

![java -jar todo-api.jar output](pictures/java-jar-todo-api-jar.png?classes=border)

The command executed the `.jar` file which started the Tomcat development server of the project. It will **stay attached to this terminal window until we are done with this article**.

{{% notice note %}}
You can stop the Tomcat development server with `ctrl`+`c`.

![ctrl + c of a running tomcat server output](pictures/tomcat-ctrl-c.png?classes=border)

Notice the terminal is back under the command of the user as displayed by the last line:

```bash
student@student-VirtualBox:~/spring-todo-api-jar
```
{{% /notice %}}

## Activity

{{% notice warning %}}
The Tomcat server will need to be running through the entire `curl` activity. The output seen will be different if the Tomcat server is not running. Verify the spring-todo-api `.jar` file is running by going through the Setup steps of this article.
{{% /notice %}}

To practice `curl` we will be sending requests to the `spring-todo-api`. It is a RESTful API that accepts HTTP `GET`, `POST`, `PATCH`, and `DELETE` requests.

The `spring-todo-api` allows the following requests:

- `GET /todos`: request a JSON list of all existing todo items
- `POST /todos` & JSON Request Body of a new Todo Item: create a new todo item
- `PATCH /todos/{id}`: changed the completed status of a todo item to `true` of the path variable `{id}`
- `DELETE /todos/{id}`: delete the todo item of path variable `{id}`

### Make a `GET` request with JSON attached

Making a `GET` request to the `spring-todo-api` will result in a list of all of the recorded todo items. As the project has just started we expect to see an empty JSON list: `[]`.

```bash
curl localhost:8080/todos -H Content-Type:application/json
```

Output:

![curl localhost:8080/todos -H Content-Type:application/json output](pictures/curl-get-json.png?classes=border)

`[]` is the expected output for this first request.

### Make a `POST` request with JSON attached

Making a `POST` request to the `spring-todo-api` and including a JSON representation of a new todo item should save the item in the todo list.

As this is a `POST` request the `-X POST` option will need to be provided.

Also a JSON representation of a new todo item will need to be sent in as the request body as indicated by the `-d` option followed by a JSON string representation of a new todo item.

```bash
curl -X POST localhost:8080/todos -H Content-Type:application/json -d '{"text":"the first task"}'
```

Output:

![curl-post-json](pictures/curl-post-json.png?classes=border)

The `spring-todo-api` is configured to return a JSON response of the newly created todo item, in this case:

```json
{"id": 1, "text": "the first todo", "completed": false}
```

{{% notice green "Bonus" "rocket" %}}
At this point as many todo items could be created by executing additional `POST` requests with valid JSON bodies.
{{% /notice %}}

### Make a `PATCH` request with JSON attached

Making a `PATCH` request requires a path variable of an existing todo item id. The API changes the completed parameter of the specific todo item (as identified by the id) to `true`.

In this case execute a `PATCH` request to first todo item created that has the id of `1`:

```bash
curl -X PATCH localhost:8080/todos/1 -H 'Content-Type:application/json'
```

Output:

![curl-patch-json](pictures/curl-patch-json.png?classes=border)


The `spring-todo-api` responded with the JSON representation of the newly updated todo item:

```json
{"id": 1, "text": "the first todo", "completed": true}
```

The `"completed"` property of the todo item was set to `true` from the original value of `false`.

{{% notice note %}}
Any existing todo item can have it's `completed` set to `true` by sending a `PATCH` request and the id of the todo item to change. This is accomplished by replacing the `{id}` portion of the above curl request which is represented with a **"1"** with a different existing todo id.
{{% /notice %}}

### Validation:

You have created a new todo through a POST request and made a minor update with a PATCH request. Check your changes with another GET request:

```bash
curl localhost:8080/todos
```

![curl-validation](pictures/curl-validation.png?classes=border)

 The `GET` requests returns a list of **all** todo items that currently exist. In this case one completed item exists. 

### Make a `DELETE` request

Making a `DELETE` request requires a valid todo item id, but is otherwise similar to the `PATCH` request.

Delete the existing todo item that we recently marked as complete:

```bash
curl -X DELETE localhost:8080/todos/1
```

The `spring-todo-api` does not return a JSON body as the the item was deleted. However, a new `GET` request will 

Output:

![curl-delete-request](pictures/curl-delete-request.png?classes=border)

{{% notice note %}}
 Additional todo items would be deleted by any `DELETE` requests that contain valid todo item ids.
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