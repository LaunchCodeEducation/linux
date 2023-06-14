---
title: "DevOps Proposal"
date: 2021-10-01T09:28:27-05:00
draft: false
hidden: true
weight: 1000
---

## Week 1: Scripting and Linux
1. Introduction to DevOps and deploying applications in the cloud. (What is the "Ops" part of DevOps and what tools are commonly used and why)
1. Overview of scripting languages (Bash, we can include Python if we would like)
1. Linux essentials for DevOps (file systems, permissions, command line tools (Linux Course))
1. Automating tasks with scripting (Linux Course has intro to Scripting and automating the process of deploying an application)
1. Version control systems (e.g., Git) and their importance in DevOps workflows (Also included within the Linux course)

## Week 2: AWS
1. Setting up an AWS account and accessing AWS resources (This will most likely include an intro to accessing our AWS account using an IAM user created for each student. We can even automate this with Terraform as a demo)
1. Understanding key AWS services for DevOps (e.g., EC2, S3, RDS) (These are the "Core" AWS resources and simply the most relavant to what the learners will most likely already know about)
1. Provisioning and managing infrastructure using AWS CloudFormation or Terraform (This process can look like the following: Completing everything within the console, take everything that we did and move it to Terraform)
1. Deploying applications on AWS (we can potentially use Digital Ocean for this class as well. There are some benefits like referring a friend to receive credits in the future.)
	- This is already included in a walkthrough or two within the AWS curriculum that has been created. We can customize it as we would like.

## Week 3: Containerization 
1. Introduction to containerization and its benefits (Why do it? What are the benefits? What kinds of architechtures use containers ie: Monolithic vs Microservices)
1. Docker fundamentals (containers, images, Dockerfile)
	- gisdevops has a what is docker and installation steps for MAC
	- gisdevops walkthrough: intro to docker includes the following:
		- common docker commands
		- simple python web app
		- creating a dockerfile
		- creating a container
		- a more complex python app
		- docker compose file
		- docker logs
1. Building and managing Docker containers (Common commands, ports to open, how to access container with shell)
1. Container orchestration with Kubernetes (Introduced with Minikube)
1. Deploying and scaling applications using Kubernetes (Can also be completed with Minikube)

## Week 4: CI/CD Pipelines
1. Continuous Integration and Continuous Deployment concepts (This is the why)
1. Setting up CI/CD pipelines using popular tools (e.g., Jenkins, GitLab CI/CD, Github Actions)
	- Jenkins hardware requirements:
		Minimum hardware requirements:
		256 MB of RAM
		1 GB of drive space (although 10 GB is a recommended minimum if running Jenkins as a Docker container)
1. Writing pipeline scripts (e.g., Jenkinsfile, GitLab CI/CD YAML, Github YAML file)
1. Automating build, test, and deployment processes
1. Monitoring and logging in CI/CD pipelines

## Week 5: Testing and Security
1. Introduction to testing methodologies (unit, integration, system testing)
1. Test automation frameworks and tools (e.g., JUnit, Selenium, Cypress)
1. Security best practices in DevOps (vulnerability scanning, secure coding practices)
1. Implementing security measures in CI/CD pipelines (Environment Variables, common problem among learners)

## Course Delivery:
1. Ideally one lead instructor and 1-2 TAs depending on the size of the class
1. I think that the walkthrough style of the Linux course is great to allow asynchronous delivery
	- This would leave space to create additional requirements for assignments for the in-class participants
1. This would allow instructors creative freedom to deliver material outside of the content within the book to expand on certain topics

## Course Content / Goals
1. I think that similar to LC101 and other courses we would want to have assignments due at the end of each week.
	- To this same regard I think that each Friday or the 5th day should leave a decent chunk of time to complete the assignment
1. In relation to a project I believe that the ideal candidate for this class already has a working application that can either be:
	- refactored in some way to be an ideal target for deployments
	- We want the learners of this course to be focused on manipulating the application so that it can be packaged, tested, and delivered with the push of a button.
	- If we decide to have the learners build their own application within a 4-5 week course my concern is that it would take too much time and be a blocker from learning other content within the course.

## Ideal Project Requirements
1. Project must be in a working state
1. Project ideally is connected to a database
1. Project must have tests
1. Any language is okay

## Template Projects
1. Provide template projects for deployment targets?

## Other Project Ideas
1. Should we have each learner deploy a hugo project that acts as their own personal website?
