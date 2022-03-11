---
title: "Initialization & First Time Deployment Script"
date: 2022-03-10T15:47:05-06:00
draft: false
weight: 1
originalAuthor: ""
originalAuthorGitHub: ""
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: ""
lastEditorGitHub: ""
lastMod: "2022-03-10"
---

## Steps

- install dependencies
- clone repository
- build artifacts
- install web server
- configure web server
- create unit file
- move build artifacts to correct location
- start system
- if system deployed successfully:
  1. email your personal email address with a success message
  1. create a cron job that fires **script two** every 5 minutes
- if system did not deploy successfully:
  1. email your personal email address with a failure message
  2. make changes to your script and try again