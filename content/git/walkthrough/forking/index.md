---
title: "Forking a Repository"
date: 
draft: false
weight: 105
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: ""
---

## Forking a Repository

A fork is simply a copy of a pre-existing repository. The major benefit of working with a forked repo is that any changes you make wont directly affect the original repository you forked. You are free to make changes to files and directories and push those changes to your forked repo. This can be very useful for your own experimentation or ideas you have that you want to add to a pre-existing project.

{{% notice note %}}
You can still submit a pull request to the original project repository you forked from your newly forked repo. Once you have made changes (preferably on a new branch: not master) you can submit that pull request through your github repo homepage. This is one way to contribute to a project as as an outside user.
{{% /notice %}}

To fork a repository you must visit the desired github project url and click on the `fork` button located near the top right portion of your window. 

![fork-repository-button](pictures/fork-repository-button.png?classes=border)

Click the `fork` button. This will be the repository you use in the remainder of the git chapter walkthroughs: `branching` and `merging`.

## Select Destination

After clicking the `fork` button github will provide you with options for the destination of the fork. Select your own personal Github user account as the location. 

<!-- TODO: Add a note, if you have previously forked the repo it may cause conflicts -->

![fork-destination](pictures/fork-destination.png?classes=border)

## Repository Forked

After selecting your own github repository you will now see that the repo has been forked and the new repo signature is `your-user-name/py-demo-web-logs` and that is has been forked from `LaunchCodeTechnicalTraining/py-demo-web-logs`

![forked-repo](pictures/forked-repo.png?classes=border)


### Recap:

This brief walkthrough is meant to server as a reminder that you are able to fork a repository in its current state to a desired location. This allows you to make changes to projects that you do not have write access to and potentially contribute to a public project.

<!-- TODO: Refactor Recap section -->

If you would like more information on forking a repo you can always view the [**Github Docs on forking**](https://docs.github.com/en/get-started/quickstart/fork-a-repo).


