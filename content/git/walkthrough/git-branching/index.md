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

- Why you should do this

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

