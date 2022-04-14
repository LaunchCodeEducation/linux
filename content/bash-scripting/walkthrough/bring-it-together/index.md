---
title: "Bring it All Together"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 120
hidden: true
originalAuthor: <no value> # to be set by page creator
originalAuthorGitHub: <no value> # to be set by page creator
reviewer: # to be set by the page reviewer
reviewerGitHub: # to be set by the page reviewer
lastEditor: # update any time edits are made after review
lastEditorGitHub: # update any time edits are made after review
lastMod: # UPDATE ANY TIME CHANGES ARE MADE
---

## Combinig Concepts

Now that you have learned how to create write a basic bash script, assign values to variables, write conditional and loop statements lets combine them all into one script!

Create a new file called `high-low.sh`

```bash
#!/bin/bash

## Create new ArrayList
high_low=(15 10 -3 5 23 -5)

## Loop through ArrayList
for item in ${high_low[@]}
do
## Compare item in list to current high_value
	if [[ $item -gt $high_value ]]
	then
		high_value=$item
	fi
## Compare item in list to current low_value
	if [[ $item -lt $low_value ]]
	then
		low_value=$item
	fi
done

## echo items to stdout and redirect: append the results into a new file
echo "The highest value is: "$high_value >> high-values.txt
echo "The lowest value is: "$low_value >> low-values.txt
```

Add the above code to the file:

Run the command `bash high-low.sh`