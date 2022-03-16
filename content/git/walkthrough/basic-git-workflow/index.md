---
title: "Review: Basic Git Workflow"
date: 2021-11-09T15:20:12-06:00
draft: false
weight: 1
originalAuthor: "John Woolbright"
originalAuthorGitHub: "jwoolbright23"
reviewer: "" # to be set by the approving reviewer
reviewerGitHub:
lastEditor: ""
lastEditorGitHub: ""
lastMod: "2022-03-16"
---

### Review: Creating a Local Git Repo

<!-- TODO: Add expectations of what we want the learner to do -->

One of the ways to use git is to initialize a local repository in a project directory you have already created. As an example you can create a new directory inside of your user home directory called `local-repository`.
- cd to your user home directory (home/student)
- make a folder called `local-repository`
- cd into your newly created directory

![local-project-directory](pictures/local-repository.png?classes=border)

Now we want to initialize git inside of this new directory we have created with the `git init` command.

{{% notice warning %}}
Make sure to cd into your newly created directory before running the `git init` command inside of your terminal.
{{% /notice %}}

![git-init](pictures/git-init-local-repo.png?classes=border)

Running the above command creates a new subdirectory named .git. This file holds all of the required repository files.

{{% notice bonus %}}
After running the `git init` command you may notice that if you type in the `ls` command it does not show the .git folder inside of our directory. Remember that we can use the `ls -a` command to show all folders within a directory, including hidden ones.
{{% /notice %}}

### Review: Creating a Remote Git Repo

There are a couple of ways to create a remote repository on git. The simplest way of doing so is to use github. After logging in you need to navigate to the repositories tab and click the green `new` button. 

![new-remote-repo](pictures/new-remote-repository.png?classes=border)

This new view gives us a few options. The only required option is to provide the remote repository with a name. For this walkthrough we will use the name `remote-repository`.

![create-remote-repo](pictures/create-remote-repo.png?classes=border)

You may be familiar with the other options:
- **Description**: Provide the new repo with a description
- **Public or Private repository**: Public (anyone on the internet can view), Private (only those you allow access can view)
- **Add a README file**: File to provide information about the project for yourself or any future users.
- **Add .gitignore**: File that allows you to ignore certain files or directories when adding, commiting, and pushing files to your remote repository. This is always something you can create later.
- **Choose a license**: We will not be covering licenses in this course. If you would like to know more please visit the [Github documentation on Licensing a Repository](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository)

For this walkthrough you should only provide this repo with a name and leave the optional settings as they were defaulted.

Click the `Create repository` button.

#### New Empty Repository

After clicking the `Create repository` button you should see the following view:

![after-create-button](pictures/after-create-button.png?classes=border)

This page provides you with options and information on how to create a new repo from the command line (which you already completed). The other option is to push an existing repo from the command line. The reason it is providing this information is because this repository is currently empty. The next step is to connect the local and remote repository so that you can share and update files between the two.

### Adding a Remote Repo to an existing Local Repo

Jump back over to the directory inside the terminal where you created a local repository.

![git-remote-add-origin](pictures/git-remote-add-origin.png?classes=border)

Once inside of the directory we can run the following command:

`git remote add origin https://github.com/"github-username"/remote-repository.git`

{{% notice note %}}
What the above command is doing is adding a new remote repository by the name of "origin" to our existing local repository. You can have as many remote repositories connected to a local repo as you would like. To add another remote you would just give it a different name. For example: `git remote add conclusion https://github.com/"github-username"/remote-repository.git`. Think of the terms "origin" and "conclusion" in this example as variables. You are giving the remote repo a name for git to reference when pushing and pulling code.
{{% /notice %}}

As you can see in the image above you are able to check if your two repositories have been connecting using the command: `git remote -v`. This command will show you all remote repositories connected to your local repository.

Your terminal should output the following information about our remote repo:
- origin `https://github.com/github-username/remote-repository.git` (fetch)
- origin `https://github.com/github-username/remote-repository.git` (push)

## Stage, Commit, and Push Local Changes

Now that you have connected your local and remote repository together you can begin to exchange folders and files between the two. Lets add an example-folder with an example-file inside of it to push to our new remote.

![example-folder-and-file](pictures/example-folder-and-file.png?classes=border)

In the picture above we created a new folder called `example-folder` and added a file to that folder called `example-file`. Lets add a small message inside of our `example-file` using nano.

![nano-example-file](pictures/nano-example-file.png?classes=border)

inside of your terminal run the command `nano example-file`.

![nano-hello-remote](pictures/nano-hello-remote.png?classes=border)

Feel free to write whatever message you would like. Just remember to write the file before exiting. You can do so using `ctrl+O` to "Write Out". Hit the enter key to save the file name and `ctrl+x` to exit nano.

Now that we have made some changes to our project directory we want to stage them for our first commit to the remote repository. 

Cd back into the root folder of this project directory using the `cd ..` command.

### Staging

Now that we are inside of the root folder we can check any changes that have been made using the `git status` command. 

![first-staging](pictures/first-staging.png?classes=border)

As you can see there are untracked files inside of our project directory. We want to stage these changes for a commit using the `git add` command.

![git-add](pictures/git-add.png?classes=border)

Type in the command `git add example-folder/` and hit the enter key. You will notice that there will not be any output after hitting enter. But if you type in `git status` once more you will see that there are now changes to be committed.

{{% notice bonus %}}
There are a couple of ways you can add files to staging. If you want to be specific like in the example above you type out the path of what folders you want to include. If you would like to include all folders and files changed into one commit you can use the command `git add .`. This will add all untracked files into staging so that you are able to commit them all at once. This is very useful if you only have a small amount of files that were changed. However if you have a large portion of untracked files you most likely want to commit them separately so that you can be more specific with your commit messages.
{{% /notice %}}

### Commit to Local Repository

Now that you have changes ready to be committed you can do so with the command `git commit`. There are a multiple things to consider when committing code to a new project repository. So before you do so lets touch base on them. 
- Meaningful Commit messages: You want your commit messages to be meaningful so that you or anyone else working on the project has a good idea of what changes were made for any given commit.
- Title, and Body of Commit: Ideally every commit has a title and a body explaining what changes were made to the file.

After considering the above lets make our first-commit. All commits usually have the following structure: `git commit -m "title of commit" -m "body message"`

![first-commit](pictures/first-commit.png?classes=border)

Enter the following command `git commit -m "first-commit" -m "added an example-folder with an example-fle containing a message"`.

#### Git Log

Now that you have made a commit you can check to see what the commit looks like using the `git log` command.

![git-log](pictures/git-log.png?classes=border)

As you can see the log shows us that a commit was made to the `master` branch from a specific `Author` on a specific `Date`. Below that you can see what the title of the commit was in addition to a description of what was included.

### Push Local Changes to Remote Repo

The final step is to push the changes that we staged and committed to our local repository up to the remote repository. To accomplish this you must use the `git push` command specifying what branch you want to push the changes to.

![git-push-origin-master](pictures/git-push-origin-master.png?classes=border)

Enter `git push origin master` into your terminal.

{{% notice note %}}
The above command is pushing changes from your local repository to the remote repository named `origin` onto the branch named `master`.
{{% /notice %}}

You will be asked for your username and password.

![git-push-origin-master-password](pictures/git-push-origin-master-password.png?classes=border)

Enter your `username` and `password` for the changes to be pushed into the remote repository.

Your remote repository should now show the added files and changes made!

![remote-repo-updated](pictures/remote-repo-updated.png?classes=border)

You can also view your commit by clicking on the `1 commit` section to view all commits inside of the remote repository.

![remote-commit-view](pictures/remote-commit-view.png?classes=border)
