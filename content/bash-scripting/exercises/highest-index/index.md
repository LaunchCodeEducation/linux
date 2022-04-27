---
title: "Index of Highest Value Script"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 110
---

## Script Requirements

- Write a script that does the following:
  - Loops through an ArrayList
  - Prints out the highest number within the list
  - Prints out the index of the highest number

{{% expand "Click Here for Solution" %}}
```bash
## Enter any numbers inside of index_list
index_list=(15 10 -3 5 23 -5)

for number in ${!index_list[@]}
do
	if [[ ${index_list[$number]} -gt $high_value ]]
	then
		high_value=${index_list[$number]}
		high_index=$number
	fi
done

echo "The highest value within the array is: "$high_value
echo "The index location of the highest value is: "$high_index
```
{{% /expand %}}