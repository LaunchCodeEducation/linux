---
title: "Forking a Repository"
date: 
draft: false
weight: 105
---

## Forking a Repository

A fork is a copy of a pre-existing repository. 

The major benefit of working with a forked repo is that any changes you make won't directly affect the original repository you forked. You are free to make changes to files and directories and push those changes to your forked repo. This can be very useful for your own experimentation or ideas you have that you want to add to a pre-existing project.

{{% notice note %}}
You can submit a pull request to the original project repository of your forked repository. Once you have made changes (preferably on a new branch: not master) you can submit that pull request through your GitHub repo homepage. This is one way to contribute to a project as as an outside contributor.
{{% /notice %}}

To fork a repository you must visit the desired github project url and click on the `Fork` button located near the top right portion of your window. 

![fork-repository-button](pictures/fork-repository-button.png?classes=border)

Click the `fork` button. This will be the repository you use in the remainder of the git chapter walkthroughs: `branching` and `merging`.

## Select Destination

After clicking the `fork` button github will provide you with options for the destination of the fork. Select your own personal Github user account as the location. 

![fork-destination](pictures/fork-destination.png?classes=border)

{{% notice note %}}
If you previously forked the project when you click the `Fork` button it will simply redirect you to your already forked version. Similarly, if you have a repository with the same name of the fork target GitHub will prompt you to enter a new name for this forked repository.
{{% /notice %}}

## Repository Forked

After selecting your own github repository you will now see that the repo has been forked and the new repo signature is `your-user-name/py-demo-web-logs` and that is has been forked from `LaunchCodeTechnicalTraining/py-demo-web-logs`

![forked-repo](pictures/forked-repo.png?classes=border)


## Recap

This brief walkthrough is meant to serve as a reminder that you are able to fork a repository in its current state to a desired location. 

This allows you to make changes to projects that you do not have write access to and potentially contribute to a public project.

## More Information

If you would like more information on forking a repo you can always view the [**Github Docs on forking**](https://docs.github.com/en/get-started/quickstart/fork-a-repo).


