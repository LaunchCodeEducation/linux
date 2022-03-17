---
title: "Creating a GitHub Issue"
date: 2022-03-08T11:15:22-06:00
weight: 2
draft: false
---

## What are GitHub Issues

GitHub Issues is a powerful feature built into GitHub that allows individuals to **raise issues** directly inside the source code of a project. These issues are monitored by the maintainers of the project and the maintainers use the information inside of an individual issue to improve the overall project.

GitHub issues often include:

- bugs
- feature requests
- found vulnerabilities
- package updating requests
- optimization requests
- and more

The maintainers of the project can use these GitHub issues to crowd source bug fixes, and plan additional work to be added to the project that are reported directly from the users.

Project maintainers have no obligation to include any suggested features, to patch any bugs or vulnerabilities, but do often use the issues to best determine what work needs to happen on any given project.

### GitHub Issues Example: `nodejs/node`

Let's take a look at the GitHub repo for the [NodeJS Project](https://github.com/nodejs/node).

![node-js-homepage](pictures/node-js-homepage.png?classes=border)

This is the standard homepage for any GitHub repository. It contains information around:

- name of organization: `nodejs`
- name of repo: `node`
- repo visibility: `Public`
- repo watchers (`2.9k`), forks (`23k`), and stars (`86.3k`)
- the current branch: `master`
- a listing of all of the directories and files in the project

You should notice a list of tabs that can be selected for more information:

- The currently selected, default tab: `<> Code`
- **`Issues`**
- `Pull requests`
- `Discussions`
- `Actions`
- `Projects`
- `Security`
- `Insights`

Let's click the **`Issues`** tab and see the currently open issues of this repo:

![node-js-issues](pictures/node-js-issues.png?classes=border)

At the time of this photo there are **1320 Open** & **12987 Closed** issues. As you may have guessed `node` is a tremendously popular and widely used programming language. In the `nodejs/node` repository bugs, vulnerabilities, possible optimizations, and new features are reported constantly for this very popular tool.

Two of the three issues we can see are clearly marked with a `feature request` label. Both of these issues are requests made by node users for the node developers to add additional features to the project.

## LaunchCode Curriculum GitHub Issues

At LaunchCode we store all of our curriculum in GitHub repositories. Our curriculum is going through constant changes and as you work through the curriculum you may find bugs, vulnerabilities, compatibility mismatches, or you may have ideas for features that can be added.

Creating a new GitHub Issue can be a daunting task. For this reason we have pre-configured **three** different GitHub Issue Templates to help you in providing us with the information we need to continue improving the curriculum.

Available LaunchCode Provided Issue Templates:

- Bug
- Clarity Request
- Feature Request

{{% notice note %}}
In addition you can open a new blank issue in which you can bring an issue to our attention outside of the three available templates.
{{% /notice %}}

## Creating a New LaunchCode GitHub Issue

### Curriculum Repository Homepage

![lctt-linux-homepage](pictures/lctt-linux-homepage.png?classes=border)

### Curriculum Repository Issues Homepage

![lctt-linux-issues-home](pictures/lctt-linux-issues-home.png?classes=border)

### Curriculum Repository Choose New Issue Template

![lctt-linux-issues-choose](pictures/lctt-linux-issues-choose.png?classes=border)

## Available Issue Templates

LaunchCode provides three Issue Templates, that we encourage you to use:

- bug
- clarity request
- feature request

### Bug

A bug issue is your way to inform us about a bug in the curriculum.

Common bugs include:
 
- a copy/edit error (misspelling, grammar mistake)
- broken links
- missing images
- un-executable code in code-fences
- buggy features (like the search, or the menu)

As you are working through the curriculum you may encounter any of the above bugs, or ones not mentioned in the list. In the case of encountering the bug we encourage you to create a new issue by using the Bug Issue Template.

#### Example

Let's take a look at the Bug Form.

![bug-form-blank](pictures/bug-form-blank.png?classes=border)

You must provide us with:

- **Title of the Issue**
  - A brief title for this issue like: `Typo on Why Learn To Code`
- The **URL** where the bug exists
  - The full URL: `https://education.launchcode.org/intro-to-professional-web-dev/chapters/introduction/why-learn-to-code.html`)
  - Or more simply, the path: `intro-to-professional-web-dev/chapters/introduction/why-learn-to-code.html`
- The **nature of the bug**
  - What bug did you encounter? 
    - How was it supposed to behave? (expected behavior)
    - How did it actually behave? (actual behavior)
  - For example: *I clicked on the Learn More link, but the resource could not be found with a 404 status code.*

Additionally, we ask that you provide any **More information** around the context of this bug. To adequately fix the bug we have to first recreate the bug on our system. This verifies the existence of the bug and gives us insight into identifying the underlying problem that is causing the bug. These steps have to be completed in order to fix the bug.

### Clarity Request

Confusion is a natural part of the learning journey. We try to create and organize content in a way that reduces confusion for as many different learning styles as possible.

There may be instances where a **large number of students and course staff** will encounter confusion around the same section of curriculum. When this happens it's a good indicator that a section should be reworded, reorganized, or rebuilt in a way to reduce the confusion experienced by a large number of individuals.

The Clarity Request Form is the mechanism that allows students and course staff to provide feedback around clarity improvements that can be made to the curriculum.

{{% notice warning %}}
**Please talk to other students and course staff about your confusion before creating a new clarity request. It is possible that the section is already in an adequate format that is meeting the needs of the majority of students and course staff. However, when a large number of students and course staff agree upon a section that is causing confusion it is an appropriate time to create a clarity request.**
{{% /notice %}}

#### Example

Let's take a look at the Clarity Request Form:

![clarity-request-form-blank](pictures/clarity-request-form-blank.png?classes=border)

You must provide us with:

- **Title of Issue**
- The **URL** to the issue
- The section of text that caused confusion: **Confusing Section**

Additionally we ask that you provide:

- Any **Suggestions** you may have for improving the clarity.
- **Additional information** to help us understand the nature of your confusion, or the underlying issue.

### Feature Request

In some instances you may have ideas about **new features** to the website hosting the curriculum, or **new content** that might have a positive impact on the experience of students and course staff working through a LaunchCode program.

Features of the website include:

- text search
- buttons
- navigation bars
- menus
  - table of contents
- next and previous buttons
- etc

Content may include:

- more code examples
- more exercises
- more concept checks
- additional sections to chapters
- additional chapters
- additional explanations
- additional definitions
- additional diagrams
- etc

There are many things that could be added to the website or to the content of the curriculum. Again we are looking for **consensus** from a **large number of students and course staff**.

In this case you need to create a Feature Request Issue.

{{% notice warning %}}
**Please talk to other students and course staff about your ideas around new content before creating a new feature request. We cannot create every feature that every individual user desires, but are very interested in adding features and content that a majority of students and course staff desire.**
{{% /notice %}}

#### Example

Let's take a look at the Feature Request Form:

![feature-request-form-blank](pictures/feature-request-form-blank.png?classes=border)

You must provide us with a **Title** and **Feature Short Description**. We must know the description of the feature you are requesting. If you cannot adequately describe to us either the new feature or content that should be added we cannot decide if the feature or content should be created.

Additionally we ask you to provide a **longer description of the feature**, and **suggestions on where/how the feature or content should be added**.

Providing as much details about the new feature or content is necessary for LaunchCode to determine if the feature / content is feasible, and if it should be developed. This makes the longer description of the feature section an important part of the form.

Providing suggestions on where the feature should be added is also important for LaunchCode to determine where and how the feature or content should be implemented.

## Review

GitHub Issues are a way for the users of a project to communicate directly with developers or maintainers of a project.

GitHub Issues are a mechanism for communicating improvements that can be made to the existing project.

LaunchCode encourages students, course staff, and allies of LaunchCode to create issues when encountering bugs, requesting new features, or requesting clarity reviews.

LaunchCode prefers students, course staff, and allies of LaunchCode to utilize the pre-existing GitHub Issues Templates (bug, feature request, clarity request), but still allows for blank issues to be raised.

## Closing Remarks

All Issues will be considered by a LaunchCode representative. However, making an issue does not guarantee that the encountered bug, clarity request, feature request or any other issue will be incorporated into the curriculum.

Any issues may be closed without discussion or reason by a LaunchCode representative.

LaunchCode reserves the final say in all things related to the curriculum.

We appreciate any and all feedback gathered through GitHub Issues and we **thank you** for your work towards creating better experiences for future students!