---
layout: post
title: Working With GIT
description: First post in git pages, just an introduction about me and about this blog. A brief description about my works and how i am about to convey them in this blog.
image: /images/working_with_git/git_logo.png
comments: true
categories: ["Welcome", "Git"]
---
If you are a software developer, its mandatory to know what **git** is. I hope this page will make you understand what git and how it will be useful to you. Before getting into practical tutorial of GIT, Let me first get you with some boring histroy and other content. When Linus Torvald was developing “Linux”, he find very difficult to manage several things like different versions of release, collaborators for the projects,.. and more. So he thought of making a framework that can address this problem. After on, he came up with a solution and named that with his behavior **GIT** (git means unpleasant man). And later on several web platform emerged to help developers to help in collaboration, version control and maintaining their projects with help of git. (Eg: github, gitlab..etc..).

This tutorial will make you in learning GIT in basics and intermediate level for working on open source projects and contributing to some libraries,..etc. There are 2 main prerequisites before starting the tutorial.
<ol>
<li> To have a Github account. https://github.com/join </li>

<li> To install git in your working system. https://git-scm.com/book/en/v2/Getting-Started-Installing-Git </li>
</ol>
To check whether GIT is installed in your system, type
```
git –version
```
*and make sure the terminal gives you the version number of the git installed (Like shown in the image below)*
![git version](/images/working_with_git/git_version.png)

There are two ways in starting a Github project.

### 1. Creating a new repository in Github and Cloning it in your local system.

Initially for creating a git project, login into your Github account and visit to this link. You will be asked for details for your projects as shown in the below image.

![git cloning link](/images/working_with_git/new_repo.png)

The details to be filled are as follows:
<ol>
<li> <bold>Repository Name :</bold> Name of your repository with which your project will be reffered.</li>

<li> Description: A short description of your project which will let other developer to look into your project.</li>

<li> Public (or) Private: You can select any one of this option. If you make your repository as Public, it will visible to all developers and anyone can contribute for your repository. The other option is making your repository Private, my doing this you can prevent people to view your repository and codes but you have to pay for making your repository as Private one. If you are a student, you can try for Github Student Developer Pack [https://education.github.com/pack] by which you can make your repository Private without paying money and also you get more free goodies with it.</li>

<li> Initialize your Repository with a README: README.md is one the important file for project. This file projects what exactly your project is?. Developing a good README.md file will add more value to your repository. You can refer this post for learning how to develope a cool README.md file.</li>

<li> Adding .gitignore file: This file tell git to not include some files to the remote repository. We will cover .gitignore in the next part of this tutorial. </li>

<li> Adding License file: If you work on a really serious project, and to protect your codes being used by other or commercial purpose,..etc.you can add a license file for your repository. There are several Types of license that can be applied for your project depending on its type, you can refer those types in this site.</li>

</ol>

After providing relevant details you can click “Create Repository” for creating your repository.

Then to add working files and codes of your project to your repository, you need to clone your repository in your local system.

For cloning a repository, you need to get the https link of your project as shown in the below image.

![git cloning link](/images/working_with_git/cloning_link.png)

After copying the Https link, go to your terminal and type
```
git clone <Https Link>
```
*as shown in the image below*

![git cloning repo](/images/working_with_git/clone_repo.png)

Then if you get into the repository folder newly created, you can see the README.md for your repository as show in the below image.

![git cloning repo](/images/working_with_git/clone_repo.png)

Great, we had successfully cloned our repository in our local System and further we can add or change files in the repository which we will discuss after after discussing on the second method of starting a Github Project.

### 2. Creating local project folder and link with the github repository.

Initially creat a Github repository as we done in the first step. Then create a new folder in your local system. Now the folder you had created is just a normal folder but you need a git supported folder for linking to your repository. So you can initialise git in the particular folder using the following command after getting into the main project folder.
```
git init
```
I had created a folder name “git_tutorial” and initialised git in that folder as shown in the below image

![git init](/images/working_with_git/git_init.png)

Now this folder is just empty one, let we link remote repository with this folder using the following command
```
git remote add origin <https link>
```
The https link is the link of your github repository which is needed to be linked. The origin refers to the local folder. Even after adding the remote repository the files are not update. So for updating the files the following command is used.
```
git pull origin master
```
The master here refers to the branch name of the remote repository.

![git pull](/images/working_with_git/git_pull.png)

Great, We had successfully linked our local project folder with the remote repository and pulled the README.md file from our repository.

Now let us start making some changes in the README.md file push back to the repository.

Let me some lines to the README.md file in the local project folder. Then this changes will be shown only in the local file and not in the remote file. For updating this change to the remote repository. We have some series of steps to be followed.

![git change1](/images/working_with_git/change1.png)

After changing the file, type the following command in the terminal
```
git status
```
Then you will see the file name that is been change had been marked in red color. Further we add the file to our stack for committing using the following command.
```
git add README.md
```
In case if you change multiple file and want to add all the file, you can use the following command.
```
git add .
```
now when check “git status”, will see that the file had been marked in green color as shown in the below image.

![git add](/images/working_with_git/git_add.png)

Then we need to commit the file for push using the following command.
```
git commit -am “<Reason for changing the file>”
```
Committing a file is necessary so that people will come to know why you changed the file. After successfully committing a file, when you check for “git status” you will see no error messages and so you file is ready to be pushed to the remote repository.

![git commit](/images/working_with_git/git_commit.png)

For pushing a committed file to the remote repository type the following command in the terminal.
```
git push origin master
```
You will be asked with the username and password for push the file. After the your file will be pushed to repository.

![git push](/images/working_with_git/git_push.png)

**And you can check the github repository for verification.**

![git changes_checked](/images/working_with_git/changes_checked.png)

Now, we know some basics on how to work with git. In next part you will get to know things like branching, pull request and many other.
