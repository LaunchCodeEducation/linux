---
title: "Loops"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 115
---

Similar to other programming languages like Java, JavaScript, and python you are also able to write `for` loops in bash:

Similar to Java, JavaScript and Python you are also able to write conditional statements in bash:

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

```bash
#!/bin/bash

for string in "Linux" "Microsoft" "Apple"
do
        echo $string
done
```

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

### While Loop

```bash
#!/bin/bash

number=0

while [ number -lt 10 ]
do
    echo $number
    ((number++))
done
```

### While Loop with Condition

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

