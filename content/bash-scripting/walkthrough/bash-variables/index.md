---
title: "Variables"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 105
---

## Creating Bash Variables

Bash is able to hold values within a variable similar to programming languages like Java, JavaScript, Python, and many more.

{{< tabs >}}
{{% tab name="Bash" %}}
```Bash
name="John"
```
{{% /tab %}}
{{% tab name="Python" %}}
```python
name = "Paul"
```
{{% /tab %}}
{{% tab name="JavaScript" %}}
```js
let name = "Paul";
```
{{% /tab %}}
{{% tab name="Java" %}}
```java
String name = "John";
```
{{% /tab %}}
{{< /tabs >}}

{{% notice note %}}
**Dissimilar** to programming languages like `JavaScript` and `Java`, `Bash` variables are not type specific. **Similar** to `Python`, `Bash` will respect any type of value you assign to a variable.
{{% /notice %}}

Syntax for initializing a variable in `bash`:

```bash
variable=value_to_hold
```
Bash variables requires there to be no whitespace on either side of the equals or `=` sign.

Calling or referencing Bash Variable:

```bash
name="Paul"
echo $name
```

To reference a bash variable you need to use a `$` in front of the variable name.
