---
title: "Exercises"
date: 2022-03-02T09:54:08-06:00
draft: false
weight: 115
originalAuthor: "Paul Matthews" # to be set by page creator
originalAuthorGitHub: "pdmxdd" # to be set by page creator
reviewer: "John Woolbright" # to be set by the page reviewer
reviewerGitHub: "jwoolbright23" # to be set by the page reviewer
lastEditor: "" # update any time edits are made after review
lastEditorGitHub: "" # update any time edits are made after review
lastMod: 2022-03-22 # UPDATE ANY TIME CHANGES ARE MADE
---

## Definite Exercise:

Full Key Logging Activity:
1. bash: on computer startup clear the logging file
1. python3: after bash file runs start the key-logging service
1. bash: on computer shutdown (email key-log file to a configured email address)

This combines the services they have seen in their walkthroughs all together to create a completely new feature that is useful. They have seen bash examples (creating a user-login file, deleting a user-login file) and python example (creating a service for a pylogger). They will have to create new unit files and start/enable the services for the bash scripts, and will need to update the pylogger service to depend on the logging clear task.

## Definite Exercise:

Create and manage services for 2-3 more web application servers (node/express, spring, .Net?, golang?) (one of which needs to have a DB component).

## Exercises

{{% children %}}