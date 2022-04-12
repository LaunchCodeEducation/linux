---
title: "Variables"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 105
originalAuthor: <no value> # to be set by page creator
originalAuthorGitHub: <no value> # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Creating Bash Variables

Bash is able to hold values within a variable similar to programming languages like Java, JavaScript, Python, and many more.
  - Syntax for creating a variable:
    - `variable=value_to_hold`
    - Bash variables requires there to be no whitespace on either side of the `=` sign.
Calling or referencing Bash Variable:
  - To reference a bash variable you need to use a `$` in front of the variable name. 
    - To reference the bash variable `bash_variable`:
      - `$bash_variable`


## Examples

- `new_variable="Hello Variable"`
  - `echo $new_variable`
- Variable within a variable:
  - `new_variable_two="Two $new_variable"`
    - `echo $new_variable_two`
- `numeric_variable=5`
- `numberic_variable_two=10`
  - `echo $numeric_variable + $numeric_variable_two`
