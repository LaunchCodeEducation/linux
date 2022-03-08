---
title: "Suggest a Change to a Page"
date: 2022-03-08T11:15:22-06:00
weight: 1
---

In the top right corner of each page you will see a link in the page menu section called `Edit this page`. Clicking this button will take you to the GitHub repository of this project. If you are currently logged in to your personal Github account you will be presented with the option of Forking the repository into your own account.

After you fork the account, you will be able to directly edit the page through the fork on your account. Once you have completed your changes, you will be prompted to title your commit, add a description of the work you completed, and to open a Pull Request back into the original Github repo.

Once you create the Pull Request LaunchCode will be able to see your requested changes and can then approve, or deny the proposed changes. If approved your changes will be merged into the master branch and will be deployed to the live site.


## Steps

Click this link will:

- take you to the `edit` route of the GitHub repository for this project.
  - if you are not already logged into GitHub you will be prompted to do so
- greeted by a banner to Fork the repository to your personal GH account
  - if you have already forked the repo, this step will be skipped
- after clicking fork, you will be redirected to your personal fork of this project
- from your fork you will be able to directly edit the file
- after making your edits you will need to create a commit title
  - optionally, but encouraged, a commit description
- click the `Propose changes` button
- which will redirect you to the creating a pull request screen
  - you will want to create a pull request from your forked project & branch into the initial project master branch
- click the `Create pull request` button
  - this creates a new pull request which will:
     - fire netlify to deploy a version of the project with your changes
       - you will be able to view your changes at the link provided, once deployment has finished
     - require a review before merge
- a LaunchCode representative will review your changes, and determine if your PR should be approved, or denied