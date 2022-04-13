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
for string in "Linux" "Ubuntu" "Microsoft" "Windows 10" "Apple" "MacOS"
do
        echo $string
done
```

{{% notice green "Bonus" "rocket" %}}
You can also loop through an array of items:
```bash
OperatingSystem=("Linux" "Ubuntu" "Microsoft" "Windows 10" "Apple" "MacOS")

for string in ${OperatingSystem[@]}
do
        echo $string
done

```
{{% /notice %}}

### For Loop with Condition

```bash
list_numbers=(1 -3 3 5 10 7 -1 15 15) 

for number in ${list_numbers[@]}
do
        if [[ $number -gt $max_number ]]
        then
                max_number=$number
        fi
        if [[ $number -lt $min_number ]]
        then
                min_number=$number
        fi
done

echo $max_number
echo $min_number
```

### While Loop

```bash
number=0

while [ number -lt 10 ]
do
    echo $number
    ((number++))
done
```

### While Loop with Condition

