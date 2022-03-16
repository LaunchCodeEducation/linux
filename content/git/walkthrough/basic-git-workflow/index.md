---
title: "Review: Basic Git Workflow"
<<<<<<< HEAD
date: 2022-16-03T15:20:12-06:00
=======
date: 2021-11-09T15:20:12-06:00
>>>>>>> git/walkthrough/basic-git-workflow/
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

<<<<<<< HEAD
## Review: Creating a Local Git Repo

<!-- TODO: Add expectations of what we want the learner to do -->

A common `git` task is to create a new directory and then initialize a git repository inside of the directory. This is likely a task you have done before, but we will be reviewing it together.

For this example you will create a new directory inside of your user home directory called `local-repository`.

- cd to your user home directory (home/student)
- make a folder called `local-repository`
- cd into your newly created directory

![local-project-directory](pictures/local-repository.png?classes=border)

Now you will need to initialize git inside of this new directory you created with the `git init` command.
=======
### Review: Creating a Local Git Repo

One of the ways to use git is to initialize a local repository in project directory you have already created. As an example you can create a new directory inside of your home/student directory called `local-repository`.

![local-project-directory](pictures/local-repository.png?classes=border)

Now we want to initialize git inside of this new directory we have created with the `git init` command.
<!-- Had to install git on virtual machine (did not come pre-installed) -->
>>>>>>> git/walkthrough/basic-git-workflow/

{{% notice warning %}}
Make sure to cd into your newly created directory before running the `git init` command inside of your terminal.
{{% /notice %}}

![git-init](pictures/git-init-local-repo.png?classes=border)

<<<<<<< HEAD
Running the above command creates a new subdirectory named `local-repository/.git/`. This file holds all of the required repository files.

{{% notice bonus %}}
After running the `git init` command you may notice that if you type in the `ls` command it does not show the .git folder inside of our directory. Remember that you can use the `ls -a` command to show all folders within a directory, including hidden ones.
{{% /notice %}}

## Review: Creating a Remote Git Repo

There are multiple ways to create a remote repository on git. The simplest way of doing so is to use GitHub. After logging in, navigate to the repositories tab and click the green `New` button. 

![new-remote-repo](pictures/new-remote-repository.png?classes=border)

The new repository page provides a wizard with a few options to create the new repository. The only required option is to provide the remote repository with a name. For this walkthrough you will use the name `remote-repository`.

![create-remote-repo](pictures/create-remote-repo.png?classes=border)

{{% notice "Bonus" "rocket" %}}
A breakdown of the remaining options:
- **Description**: Provide the remote repo with a description
- **Public or Private repository**: Public (anyone on the internet can access), Private (only those with proper authentication can access)
- **Add a README file**: File to provide information about the project.
- **Add .gitignore**: File that instructs the local & remote repository to ignore certain files or directories. Files will be completely ignored when performing `git commands` (likeadding, commiting, and pushing).
- **Choose a license**: The license for the project. We will not be covering licenses in this course. If you would like to know more please visit the [Github documentation on Licensing a Repository](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository)
{{% /notice %}}

For this walkthrough you should only **provide this repo with a name** and leave the optional settings as they were defaulted.

Click the `Create repository` button.

### New Empty Repository

After clicking the `Create repository` button you should see the following view:

![after-create-button](pictures/after-create-button.png?classes=border)

This page provides you with instructions for using this remote repository.

You can:

- create a new local repository from the command line, and add this remote repository to the local repository.
- push an existing local repository to this empty remote repository, after adding this remote repository to your local repository.
- import code from another repository.

As you have already completed the steps of the first option, we will be walking through that option.

We already created the directory (`local-repository`) and initialized it as a local repository (`local-repository/.git`).

We now need to add the new remote repository to our local repository. This is how it knows where to push and pull from.

## Adding a Remote Repo to an existing Local Repo
=======
Running the above command creates a new subdirectory named .git. This file holds all of the required repository files.

### Review: Creating a Remote Git Repo

There are a couple of ways to create a remote repository on git. The simplest way of doing so is to use the github. After logging in you need to navigate to the repositories tab and click the green `new` button. 

![new-remote-repo](pictures/new-remote-repo.png?classes=border)

This new view gives us a few options. The only required option is to provide the remote repository with a name. For this walkthrough we will use the name `remote-repository`.

You may be familiar with the other options:
- **Description**: Provide the new repo with a description
- **Public or Private repository**: Public (anyone on the internet can view), Private (only those you allow access can view)
- **Add a README file**: File to provide information about the project for any future users
- **Add .gitignore**: File that allows you to ignore certain files or directories when adding, commiting, and pushing files to your remote repository. This is always something you can create later.
- **Choose a license**:
<!-- TODO: Create note about License and what the general purposes are -->

For this walkthrough you should only provide this repo with a name and leave the optional settings as they were defaulted.

![create-remote-repo](pictures/create-remote-repo.png?classes=border)

Click the `Create repository` button.

After clicking the Create button you should see the following view:

![after-create-button](pictures/after-create-button.png?classes=border)

This page provides you with options and information on how to create a new repo from the command line (which you already completed). The other option is to push an existing repo from the command line. The reason it is providing this information is because this repository is currently empty. The next step is to connect our local and remote repository so that we can push something (code, files, folders) into the repository.

### Link a Remote Repo to Local Repo
>>>>>>> git/walkthrough/basic-git-workflow/

Jump back over to the directory inside the terminal where you created a local repository.

![git-remote-add-origin](pictures/git-remote-add-origin.png?classes=border)

Once inside of the directory we can run the following command:

`git remote add origin https://github.com/"github-username"/remote-repository.git`

<<<<<<< HEAD
{{% notice note %}}
The above command is adding a new remote repository by the name of "origin" to our existing local repository. You can have as many remote repositories connected to a local repo as you would like. To add another remote you would just give it a different name. For example: `git remote add conclusion https://github.com/"github-username"/remote-repository.git`. Think of the terms "origin" and "conclusion" in this example as variables. You are giving the remote repo a name for git to reference when pushing and pulling code.
{{% /notice %}}

The second command in the image above is: `git remote -v`. This command will show you all of the remote repositories connected to your local repository.
=======
As you can see in the image above you are able to check if your two repositories have been connecting using the command: `git remote -v`.
>>>>>>> git/walkthrough/basic-git-workflow/

Your terminal should output the following information about our remote repo:
- origin `https://github.com/github-username/remote-repository.git` (fetch)
- origin `https://github.com/github-username/remote-repository.git` (push)

<<<<<<< HEAD
## Stage, Commit, and Push Local Changes

Now that you have added you remote repository (`origin`) to your local repository you can begin to synchronize folders and files between the two. Lets add an example-folder with an example-file inside of it to push to our new remote.
=======
### Stage, Commit, and Push Local Changes

Now that you have connected your local and remote repositories you can push local information into our remote repository. Lets add an example-folder with an example-file inside of it to push to our new remote.
>>>>>>> git/walkthrough/basic-git-workflow/

![example-folder-and-file](pictures/example-folder-and-file.png?classes=border)

In the picture above we created a new folder called `example-folder` and added a file to that folder called `example-file`. Lets add a small message inside of our `example-file` using nano.

![nano-example-file](pictures/nano-example-file.png?classes=border)

inside of your terminal run the command `nano example-file`.

![nano-hello-remote](pictures/nano-hello-remote.png?classes=border)

Feel free to write whatever message you would like. Just remember to write the file before exiting. You can do so using `ctrl+O` to "Write Out". Hit the enter key to save the file name and `ctrl+x` to exit nano.

Now that we have made some changes to our project directory we want to stage them for our first commit to the remote repository. 

<<<<<<< HEAD
Change back into the root folder of this project directory using the `cd ..` command.

### Staging

Now that we are inside of the root folder we can check any changes that have been made using the `git status` command. 

![first-staging](pictures/first-staging.png?classes=border)

As you can see there are untracked files inside of our project directory. We want to stage these changes for a commit using the `git add` command.

![git-add](pictures/git-add.png?classes=border)

Type in the command `git add example-folder/` and hit the enter key. You will notice that there will not be any output after hitting enter. But if you type in `git status` once more you will see that there are now changes to be committed, in this case `new file: example-folder/example-file`.

{{% notice bonus %}}
There are a couple of ways you can add files to staging. If you want to be specific like in the example above you type out the path of what folders or files you want to include. If you would like to add all folders and files changed into staging you can use the command `git add .`. This will add all untracked files into staging so that you are able to commit them all at once. This is very useful if you only have a small amount of files that were changed. However if you have a large portion of untracked files you most likely want to commit them separately so that you can be more specific with your commit messages.
{{% /notice %}}

### Commit to Local Repository

Now that you have changes ready to be committed you can do so with the command `git commit`. There are a multiple things to consider when committing code to a new project repository. So before you do so lets touch base on them. 

- **Meaningful Commit messages**: You want your commit messages to be meaningful so that you or anyone else working on the project has a good idea of what changes were made for any given commit.
- **Title, and Body** of Commit: Ideally every commit has a title and a body explaining what changes were made to the file.

After considering the above lets make our first-commit. All commits usually have the following structure: `git commit -m "title of commit" -m "body message"`
=======
Cd back into the root folder of this project directory using the `cd ..` command.

![first-staging](pictures/first-staging.png?classes=border)

## Staging

Now that we are inside of the root folder we can check any changes that have been made using the `git status` command. As you can see there are untracked files inside of our project directory. We want to stage these changes for a commit using the `git add` command.

![git-add](pictures/git-add.png?classes=border)

Type in the command `git add example-folder/` and hit the enter key. You will notice that there will not be any output after hitting enter. But if you type in `git status` once more you will see that there are now changes to be committed.

## Commit Local Changes

Now that you have changes ready to be committed we can do so with the following command `git-commit`. There are a multiple things to consider when committing code to a new project repository. So before we do so lets touch base on them. 
- Meaningful Commit messages: You want your commit messages to be meaningful so that you or anyone else working on the project has a good idea of what changes were made for any given commit.
- Title, and Body of Commit: Ideally every commit has a title and a body explaining what changes were made to the file.

After considering the above lets make our first-commit. All commit commands usually have the following structure: `git commit -m "title message" -m "body message"`
>>>>>>> git/walkthrough/basic-git-workflow/

![first-commit](pictures/first-commit.png?classes=border)

Enter the following command `git commit -m "first-commit" -m "added an example-folder with an example-fle containing a message"`.

<<<<<<< HEAD
{{% notice note %}}
In some instances you may want to create a commit with just a title. In this case you would simply use the `git commit -m "title"` command. We recommend providing titles, and bodies to your commits, but it is not necessary.
{{% /notice %}}

#### Git Log

Now that you have made a commit you can check to see what the commit looks like using the `git log` command.

![git-log](pictures/git-log.png?classes=border)

As you can see the log shows us that a commit was made to the `master` branch from a specific `Author` on a specific `Date`. Below that you can see what the title of the commit was in addition to a description of what was included.

### Push Local Changes to Remote Repo

The final step is to push the changes that we staged and committed in our local repository to the remote repository. To accomplish this you must use the `git push` command specifying what branch you want to push the changes to.

![git-push-origin-master](pictures/git-push-origin-master.png?classes=border)

Enter `git push origin master` into your terminal.

{{% notice note %}}
The above command is pushing changes from your local repository to the remote repository named `origin` onto the branch named `master`. In this case your remote repository doesn't have any branches, or files. This push will create the branch `master` with all committed work to the remote repository.
{{% /notice %}}
=======

### Push Local Changes to Remote Repo

The final step is to push the changes that we staged and committed to our remote repository. This is as simple as using the `git push` command specifying what branch we want to push our changes to.

![git-push-origin-master](pictures/git-push-origin-master.png?classes=border)

Enter the `git push origin master` command into your terminal.
>>>>>>> git/walkthrough/basic-git-workflow/

You will be asked for your username and password.

![git-push-origin-master-password](pictures/git-push-origin-master-password.png?classes=border)

<<<<<<< HEAD
Enter your `username` and `password` for the changes to be pushed into the remote repository.

Your remote repository should now contain the added files and changes made!

![remote-repo-updated](pictures/remote-repo-updated.png?classes=border)

You can also view your commit by clicking on the `1 commit` section to view all commits inside of the remote repository.

![remote-commit-view](pictures/remote-commit-view.png?classes=border)

## Recap:

This walkthrough was a refresher on the following:

- Creating a local repository
  - `git init`
- Creating a remote repository on github
- Adding a remote repo to our local repo
  - `git remote add <remote-reference-name> <remote-repository-url>`
- Staging, Committing, and Pushing local changes to a remote repository
  - `git add`, `git commit`, `git push`
=======
>>>>>>> git/walkthrough/basic-git-workflow/
