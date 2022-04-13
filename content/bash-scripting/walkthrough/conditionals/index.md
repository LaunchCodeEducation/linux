---
title: "Conditionals"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 110
---

## Conditional Statements in Bash

Similar to Java, JavaScript and Python you are also able to write conditional statements in bash:

{{< tabs >}}
{{% tab name="Bash" %}}
```Bash
if [[ condition ]]
then 
    clause statement
fi
```
{{% /tab %}}
{{% tab name="Python" %}}
```python
if condition:
    clause statement
```
{{% /tab %}}
{{% tab name="JavaScript" %}}
```js
if (condition) {
    clause statement
}
```
{{% /tab %}}
{{% tab name="Java" %}}
```java
if (condition) {
    clause statement
}
```
{{% /tab %}}
{{< /tabs >}}

{{% notice note %}}
Notice that `bash` requires a closing "`fi`" for `if` statements.
{{% /notice %}}

## Examples

### if Statement

Create a new file called `if-condition`.

```bash
#!/bin/bash

number1=10

if [[ $number1 eq 10 ]]
then
    echo "$number1 is equal to 10!"
fi
```

Save the above code to the `if-condition` file and exit the editor.

Run the command `bash if-condition`.

![if-condition](pictures/if-condition.png?classes=border)

### if else statement

Create a new file called `example-if-else`.

```bash
#!/bin/bash

number1=1
number2=2

if [[ $number1 -gt $number2 ]]
then
    echo "The first number is higher"
else
    echo "The second number is higher"
fi
```

Save the above code to the `example-if-else` file and exit the editor.

Run the command `bash example-if-else`.

![example-if-else](pictures/example-if-else.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
Try changing the values of the variables to test different outcomes!
{{% /notice %}}

### if elif else statement

Create a new file called `if-elif-else`.

```bash
#!/bin/bash

$new_number1=50

if [[ $new_number -lt 50 ]]
then
    echo "The number is less than 50"
elif [[ $new_number -eq 50 ]]
then
    echo "The number is equal to 50"
else
    echo "The number is greater than 50"
fi
```

Save the above code to the `if-elif-else` file and exit the editor.

Run the command `bash if-elif-else` and try to match each test case:

![if-elif-else](pictures/if-elif-else.png?classes=border)






