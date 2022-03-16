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

One of the ways to use git is to initialize a local repository in project directory you have already created. As an example you can create a new directory inside of your home/student directory called `local-repository`.

![local-project-directory](pictures/local-repository.png?classes=border)

Now we want to initialize git inside of this new directory we have created with the `git init` command.
<!-- Had to install git on virtual machine (did not come pre-installed) -->

{{% notice warning %}}
Make sure to cd into your newly created directory before running the `git init` command inside of your terminal.
{{% /notice %}}

![git-init](pictures/git-init-local-repo.png?classes=border)

Running the above command creates a new subdirectory named .git. This file holds all of the required repository files.

<!-- TODO: Add bonus of how to find the .git folder -->

### Review: Creating a Remote Git Repo

There are a couple of ways to create a remote repository on git. The simplest way of doing so is to use the github. After logging in you need to navigate to the repositories tab and click the green `new` button. 

![new-remote-repo](pictures/new-remote-repository.png?classes=border)

This new view gives us a few options. The only required option is to provide the remote repository with a name. For this walkthrough we will use the name `remote-repository`.

You may be familiar with the other options:
- **Description**: Provide the new repo with a description
- **Public or Private repository**: Public (anyone on the internet can view), Private (only those you allow access can view)
- **Add a README file**: File to provide information about the project for any future users
- **Add .gitignore**: File that allows you to ignore certain files or directories when adding, commiting, and pushing files to your remote repository. This is always something you can create later.
- **Choose a license**:
<!-- TODO: Create note about License and what the general purposes are -->
<!-- we will not be covering licenses in this course. -->

For this walkthrough you should only provide this repo with a name and leave the optional settings as they were defaulted.

![create-remote-repo](pictures/create-remote-repo.png?classes=border)

Click the `Create repository` button.

After clicking the Create button you should see the following view:

![after-create-button](pictures/after-create-button.png?classes=border)

This page provides you with options and information on how to create a new repo from the command line (which you already completed). The other option is to push an existing repo from the command line. The reason it is providing this information is because this repository is currently empty. The next step is to connect our local and remote repository so that we can push something (code, files, folders) into the repository.

### Adding a Remote Repo to an existing Local Repo

Jump back over to the directory inside the terminal where you created a local repository.

![git-remote-add-origin](pictures/git-remote-add-origin.png?classes=border)

<!-- TODO: add in a snippet about what the "origin" is when adding a new remote repository -->

Once inside of the directory we can run the following command:

`git remote add origin https://github.com/"github-username"/remote-repository.git`

As you can see in the image above you are able to check if your two repositories have been connecting using the command: `git remote -v`.

Your terminal should output the following information about our remote repo:
- origin `https://github.com/github-username/remote-repository.git` (fetch)
- origin `https://github.com/github-username/remote-repository.git` (push)

## Stage, Commit, and Push Local Changes

Now that you have connected your local and remote repositories you can push local information into our remote repository. Lets add an example-folder with an example-file inside of it to push to our new remote.

![example-folder-and-file](pictures/example-folder-and-file.png?classes=border)

In the picture above we created a new folder called `example-folder` and added a file to that folder called `example-file`. Lets add a small message inside of our `example-file` using nano.

![nano-example-file](pictures/nano-example-file.png?classes=border)

inside of your terminal run the command `nano example-file`.

![nano-hello-remote](pictures/nano-hello-remote.png?classes=border)

Feel free to write whatever message you would like. Just remember to write the file before exiting. You can do so using `ctrl+O` to "Write Out". Hit the enter key to save the file name and `ctrl+x` to exit nano.

Now that we have made some changes to our project directory we want to stage them for our first commit to the remote repository. 

Cd back into the root folder of this project directory using the `cd ..` command.

![first-staging](pictures/first-staging.png?classes=border)

### Staging

Now that we are inside of the root folder we can check any changes that have been made using the `git status` command. As you can see there are untracked files inside of our project directory. We want to stage these changes for a commit using the `git add` command.

![git-add](pictures/git-add.png?classes=border)

Type in the command `git add example-folder/` and hit the enter key. You will notice that there will not be any output after hitting enter. But if you type in `git status` once more you will see that there are now changes to be committed.

### Commit to Local Repository

Now that you have changes ready to be committed we can do so with the following command `git-commit`. There are a multiple things to consider when committing code to a new project repository. So before we do so lets touch base on them. 
- Meaningful Commit messages: You want your commit messages to be meaningful so that you or anyone else working on the project has a good idea of what changes were made for any given commit.
- Title, and Body of Commit: Ideally every commit has a title and a body explaining what changes were made to the file.

After considering the above lets make our first-commit. All commit commands usually have the following structure: `git commit -m "title message" -m "body message"`

![first-commit](pictures/first-commit.png?classes=border)

<!-- TODO: Have them complete a git log and check the remote repo -->

Enter the following command `git commit -m "first-commit" -m "added an example-folder with an example-fle containing a message"`.


### Push Local Changes to Remote Repo

The final step is to push the changes that we staged and committed to our remote repository. This is as simple as using the `git push` command specifying what branch we want to push our changes to.

![git-push-origin-master](pictures/git-push-origin-master.png?classes=border)

Enter the `git push origin master` command into your terminal.

You will be asked for your username and password.

![git-push-origin-master-password](pictures/git-push-origin-master-password.png?classes=border)

<!-- TODO: Have them complete another git log and check the remote repo here -->

Enter your `username` and `password` for the changes to be pushed into the remote repository.

Your remote repository should now show the added files and changes made!

![remote-repo-updated](pictures/remote-repo-updated.png?classes=border)
