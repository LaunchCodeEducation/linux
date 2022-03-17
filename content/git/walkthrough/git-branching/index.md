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

## Branching

Branching is a crucial compenent when working with projects under version control. Branching allows you to diverge from the master or main branch of a project directory so that you can make changes safely. It is best practice to always create a new branch when adding content to a project.

When creating a new branch you always want to make sure your master branch is updated to the most recent version. That process will look something like the following..
- `git checkout master` (if not already on the master branch)
- `git pull`: Update master branch to most recent working version
- `git checkout -b new-branch-name`: Create the new branch to work
{{% notice note %}}
We are "checking out" from master so that we are adding code to the master branch version of the project. If you were to checkout from a different branch you would be working with the code from that specific branch (which most likely wont have been merged with master yet).
{{% /notice %}}
- `git branch`: Check that you are on the correct branch

<!-- - Why you should do this -->

{{< mermaid >}}
gitGraph:
options
{
  "nodeSpacing: 75,
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

