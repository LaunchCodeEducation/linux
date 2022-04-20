---
title: "Loops"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 115
---

## Looping with Bash

Similar to other programming languages like Java, JavaScript, and python you are also able to write `for` loops in bash:

{{< tabs >}}
{{% tab name="Bash" %}}
```Bash
for item in [LIST]
do
  [COMMANDS]
done

```
{{% /tab %}}
{{% tab name="Python" %}}
```python
for element in collection:
    loop body
```
{{% /tab %}}
{{% tab name="JavaScript" %}}
```js
for (Virable Initialization; Loop Exit Condition; Variable Modification) {
    loop body
}
```
{{% /tab %}}
{{% tab name="Java" %}}
```java
for (Variable Initialization; Loop Exit Condition; Variable Modification) {
    loop body
}
```
{{% /tab %}}
{{< /tabs >}}

You can also write `while` loops:

{{< tabs >}}
{{% tab name="Bash" %}}
```Bash
while [CONDITION]
do
  [COMMANDS]
done

```
{{% /tab %}}
{{% tab name="Python" %}}
```python
while condtion:
    loop body
```
{{% /tab %}}
{{% tab name="JavaScript" %}}
```js
while (condition) {
    loop body
}
```
{{% /tab %}}
{{% tab name="Java" %}}
```java
while (condition) {
    loop body
}
```
{{% /tab %}}
{{< /tabs >}}

{{% notice note %}}
Notice that bash requires a closing `done` statement to end the loop.
{{% /notice %}}

## Examples

### For Loop

Create a new file called `for-loop.sh`

```bash
#!/bin/bash

for string in "Linux" "Microsoft" "Apple"
do
        echo $string
done
```

Save the above code to the `for-loop.sh` file and exit the editor.

Run the command `bash for-loop.sh`:

![for-loop](pictures/for-loop.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
You can also loop through an array of items:
```bash
#!/bin/bash

OperatingSystem=("Linux" "Microsoft" "Apple")

for string in ${OperatingSystem[@]}
do
        echo $string
done

```
{{% /notice %}}

### For Loop with Condition

Create a new file called `for-loop-if-else.sh`

```bash
#!/bin/bash

OperatingSystem=("Linux" "Microsoft" "Apple")

for string in ${OperatingSystem[@]}
do
        if [[ $string == "Linux" ]]
        then
                echo $string: "Open Source!"
        else
                echo $string: "Not Open Source : ("
        fi
done
```

Save the above code to the `for-loop-if-else.sh` file and exit the editor.

Run the command `bash for-loop-if-else.sh`:

![for-loop-condition](pictures/for-loop-condition.png?classes=border)

### While Loop

Create a new file called `while-loop.sh`

```bash
#!/bin/bash

number=0

while [ $number -lt 10 ]
do
    echo $number
    ((number++))
done
```

Save the above code to the `while-loop.sh` file and exit the editor.

Run the command `bash while-loop.sh`:

![while-loop](pictures/while-loop.png?classes=border)

### While Loop with Condition

Create a new file called `while-loop-if.sh`

```bash
#!/bin/bash

number=0

while [ $number -lt 10 ]
do
        echo $number
        ((number++))
        if [[ $number -eq 5 ]]
        then
                echo "halfway done!"
        fi
done
```

Save the above code to the `while-loop-if.sh` file and exit the editor.

Run the command `bash while-loop-if.sh`:

![while-if-loop](pictures/while-if-loop.png?classes=border)

## Recap:
- For loop
  - For loop with conditional statement
- While loop
  - While loop with conditional statement

