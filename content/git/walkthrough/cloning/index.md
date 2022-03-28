---
title: "Cloning a Repository"
date: 2022-16-03T15:20:12-06:00
draft: false
weight: 110
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: "John Woolbright"
lastEditorGitHub: "jwoolbright23"
lastMod: "2022-03-28"
---

{{% notice note %}}
We will be using the Repository forked in the previous walkthrough for the instructions below
{{% /notice %}}

## Git Clone

Cloning a repo will work for any repository on github. An original project, a forked project, or a project you have created previously that you would like to access on a new machine. The command used to accomplish this task is `git clone`. 

The main purpose of cloning a repository is to access remote files *locally* so that you can review or make changes to those files.

There are a few ways to clone a repository. The simplest way is to grab the github project url and run the `git clone` command inside of your terminal.

### Copy Github Project URL

First things first, grab the desired github url from your repository by hitting the green `Code` button and copying the link within to your clipboard.

![git-clone-button](pictures/git-clone-button.png?classes=border)

Now open up a new terminal and navgiate to the directory where you want the project to live. In the below example you will see that we are cloning the project into the `Desktop` directory.

![git-clone-desktop](pictures/git-clone-desktop.png?classes=border)

{{% notice warning %}}
make sure to replace `/your-github-user/` with your own personal github username while also inside the directory where you want the project to live.
{{% /notice %}}

run the command `git clone https://github.com/your-github-user/py-demo-web-logs.git` in the terminal.

This will create a new directory (inside of your current working directory) named `py-demo-web-logs`, initialize a .git directory, and grab all of the most recent data associated with the repository.

If you run the `ls` command you can see that the folder has been cloned:

![cloned-directory-ls](pictures/cloned-directory-ls.png?classes=border)

{{% notice green "Bonus" "rocket" %}}
You can also clone a repository and provide it a new name should you ever wish to do so. You can accomplish this by adding the name you want the directory to be called at the end of the command: `git clone https://github.com/your-github-user/py-demo-web-logs.git <newdirectoryname>`
![new-name-example](pictures/new-name-example.png?classes=border)
{{% /notice %}}

### Explore Cloned Local Files

Now that you have cloned a repository onto your machine you can access the files locally. Take a look at what the `py-demo-web-logs` contains.

Navigate into the newly cloned directory and run the `ls` command once more. You will see that there is a `main.py` file located within.

![ls-py-demo-web-logs](pictures/ls-py-demo-web-logs.png?classes=border)

{{% notice note %}}
In the upcoming `branching` walkthrough we will be creating a new branch inside of this project directory and fixing a bug located within the main.py file of our `py-demo-web-logs`.
{{% /notice %}}

### Recap:

This walkthrough was a refresher on the following:
- Cloning a Repository
  - `git clone https://github.com/git-repo-url`