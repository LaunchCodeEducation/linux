---
title: "Working with Branches"
date: 2022-17-03T15:20:12-06:00
draft: false
weight: 3
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: ""
lastEditorGitHub: ""
lastMod: "2022-03-17"
---

## Creating a new Branch

While inside of a git project directory you can create a new branch with the `git branch` command. To test this you can do the following:

Navigate your terminal to an existing project and run the command `git branch`. This will show you the current branch you are working on in addition to any other local branches you have.

![git-branch-command](pictures/git-branch-command.png?classes=border)

{{% notice bonus %}}
If you would like to view all local branches in addition to any remote branches you can add the -a tag at the end of your command: `git branch -a`. Try it out!
{{% /notice %}}

Now run the command `git branch new-branch`. 

![git-new-branch](pictures/git-new-branch.png?classes=border)

Once again you can check the status of your branches with `git branch` or `git branch -a`.

## Changing Branches

Now that you have a new branch to work on you can switch or "checkout" to that branch with the `git checkout` command.

![git-checkout](pictures/git-checkout.png?classes=border)

Run the command `git checkout new-branch`. Once more check your current branch status with the `git branch` command.

Now that you are on your newly created branch you can begin to add content safely.

<!-- Branching is a crucial compenent when working with projects under version control. Branching allows you to diverge from the master or main branch of a project directory so that you can make changes safely. It is best practice to always create a new branch when adding content to a project.

When creating a new branch you always want to make sure your master branch is updated to the most recent version. That process will look something like the following:

![git-branch-create](pictures/git-branch-create.png?classes=border)

- `git checkout master` (if not already on the master branch)
- `git pull`: Update master branch to most recent working version
- `git checkout -b new-branch-name`: Create the new branch to work on
{{% notice note %}}
We are "checking out" from master so that we are adding code to the master branch version of the project. If you were to checkout from a different branch you would be working with the code from that specific branch (which most likely wont have been merged with master yet). The above is also a shortened way of creating a new branch with `git branch new-branch` >> `git checkout new-branch`
{{% /notice %}}
- `git branch`: Check that you are on the correct branch

{{% notice bonus %}}
To view all remote branches you can use the command `git branch -a`
{{% /notice %}} -->

<!-- - Why you should do this -->

## Branch Diagram

Below you will find a diagram vizualizing the creation of a new branch and making commits. You are also able to see the branch being merged into master.

{{< mermaid >}}
gitGraph:
options
{
  "nodeSpacing: 50,
  "nodeRadius": 10
}
end
  commit
  branch newbranch
  checkout newbranch
  commit
  commit
  checkout master
  commit
  commit
  merge newbranch
{{< /mermaid >}}


### `git branch`

- example repo
  - broken app with a bug
  - new branch to fix bug
- example repo2
  - app that is being expanded
  - new branch for new feature
- after coding pushed up and 

