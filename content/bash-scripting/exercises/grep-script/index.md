---
title: "Scripting Grep"
date: 2022-04-08T13:54:20-05:00
draft: false
weight: 105
---

## Script Requirements:
- Get Dataset located at `https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv`
  - write it to a file called `user-data` in your `home` directory.
- Create a new directory called `technical-user-data` inside of the `home directory`
- Filter the Data inside of `user-data` to include only lines matching `Paul` and write the results to a file called `paul-data.csv` inside of the `technical-user-data` directory
- Filter the Data inside of the `paul-data.csv` file to only include results with `Centene` as the employer and write to a new file called `paul-employer-centene.csv` inside of the `technical-user-data` directory
- Filter the Data inside of the `paul-employer-centene.csv` file to only include users with emails ending with `example.net` to a new file called `final-paul-user-data.csv` inside of the `technical-user-data` directory


{{% expand "Click Here for Answer" %}}
```bash
curl -s https://launchcodetechnicaltraining.org/api/walkthrough/user?data_format=csv > ~/user-data

mkdir ~/technical-user-data

cat ~/user-data | grep "^Paul," > ~/technical-user-data/paul-data.csv

cat ~/technical-user-data/paul-data.csv | grep "Centene$" > ~/technical-user-data/paul-employer-centene.csv

cat ~/technical-user-data/paul-employer-centene.csv | grep "@example\.net" > ~/technical-user-data/final-paul-user-data.csv
```
{{% /expand %}}