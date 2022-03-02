---
title: "Bash Command: echo"
date: 2022-02-17T14:54:25-06:00
draft: false
weight: 6
reviewer: "" # to be set by the approving reviewer
last_editor: "" # update each time the file is edited
last_edit_date: # just the date is enough (don't worry about the time portion)
---

## `echo`

The next command `echo` simply prints out a message to the Bash shell's Standard Output (STDOUT). An echo statement is very similar to the `print()` method in Python3, or the `console.log()` method in JavaScript, or the `System.out.println()` method in Java. View the following code snippets to see how you can display "hello" using Python, JavaScript, Java, and the Bash echo command.

{{< tabs >}}
{{% tab name="python" %}}
```python
print("Hello")
```
{{% /tab %}}
{{% tab name="JavaScript" %}}
```js
> console.log("Hello")
```
{{% /tab %}}
{{% tab name="Java" %}}
```java
System.out.println("Hello")
```
{{% /tab %}}
{{% tab name="Bash" %}}
```Bash
echo "Hello"
```
{{% /tab %}}
{{< /tabs >}}

To use the `echo command` we simply need to invoke the command with one argument that results in a string.

Enter `echo "Hello world"`.

![echo "hello world"](pictures/echo-hello-world.png?classes=border)

{{% notice note %}}
`echo` commands are especially useful inside of Bash scripts. In any given Bash script many things may be happening and outputting some message to the individual that invokes the script is a very useful feature.
{{% /notice %}}

The `echo` command can be used to easily view the contents of a Shell Variable. Your home directory, path, and many other variables are attached directly to your Bash Shell in the form of variables. You can use `echo $VARIABLE` to easily view the contents of the variable.