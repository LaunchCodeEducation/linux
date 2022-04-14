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

## Operators

Bash has built in binary operators for the following:
- equal to: `-eq`
- not equal to: `-ne`
- less than: `-lt`
- less than or equal to: `le`
- greater than: `-gt`
- greater than or equal to: `-ge`

Some of the above operators will be used in the following walkthroughs for the `Bash: Scripting` chapter.

## Examples

### if Statement

Create a new file called `if-condition.sh`.

```bash
#!/bin/bash

number1=10

if [[ $number1 -eq 10 ]]
then
    echo "$number1 is equal to 10!"
fi
```

Save the above code to the `if-condition.sh` file and exit the editor.

Run the command `bash if-condition.sh`.

![if-condition](pictures/if-condition.png?classes=border)

### if else statement

Create a new file called `if-else-condition.sh`.

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

Save the above code to the `if-else-condition.sh` file and exit the editor.

Run the command `bash if-else-condition.sh`.

![example-if-else](pictures/example-if-else.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
Try changing the values of the variables to test different outcomes!
{{% /notice %}}

### if elif else statement

Create a new file called `if-elif-else.sh`.

```bash
#!/bin/bash

new_number=50

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

Save the above code to the `if-elif-else.sh` file and exit the editor.

![bash-if-elif-else](pictures/bash-if-elif-else.png?classes=border)

Run the command `bash if-elif-else.sh`.

Try changing the value of `new_number`!

{{% notice green "Bonus" "rocket" %}}
You can also read from `stdin` and assign a variable with bash to make a script more interactive. Create a new file called `read-stdin-example.sh`. 

Add the code below:

```bash
#!/bin/bash

echo "Please enter a number: "
read number_value

if [[ $number_value -lt 50 ]]
then
    echo "The number $number_value is less than 50"
elif [[ $number_value -eq 50 ]]
then
    echo "The number $number_value is equal to 50"
else
    echo "The number $number_value is greater than 50"
fi
```
Run the command `bash read-stdin-example.sh`

![read-stdin-example](pictures/read-stdin-example.png?classes=border)
{{% /notice %}}





