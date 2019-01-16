---
layout: post
title:  "Using Git for Game Development"
categories: programming tutorials
---

Source control can be daunting but it is pretty important for sharing with others and backing up to prevent data loss. 
I will cover installing git on a windows environment, using online repositories (repos) and getting a Unity game setup on git.

{% include post-styling.md %}


# Git and What it Does

Pulled from the [site](https://git-scm.com) Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. 
There are other version control systems like subversion but Git is the most popular and widespread.

# Setup and Visual Git Editors

For windows, we can grab the download right from the git website. https://git-scm.com/download/win  

Following the instructions, it will setup defaults and access to git from the command line. 
This is the default way to use git but I personally use visual editors for commiting and pushing to remote repos.
Once in the install is down you should be able to open the command line or powershell and type in `git --version` and get something like
`git version 2.19.0.windows.1`
There is a lot of documentation so if you plan on using the command line, [read up](https://git-scm.com/docs)

## Visual editors

I personally use a visual editor. I do have to revert to the commands every once in a while to fix things but for the most part I use visual GUIs.

### [Gitkraken](https://www.gitkraken.com/git-client)

My preferred git editor. It has a lot of features that I like and is usually fast. 
The free version limits you to one account email and name versus the pro version gives you access to more profiles. 
This is handy so you can commit with different emails between say your work email or your personal email. It has a yearly subscription for the pro features so keep that in mind if you plan on using it.

![gitkrakengif](/assets/img/posts/gitgamedev/gk-merge-edit.gif){: .image-sized .center-image }  

This is my referral link if you want to sign up and try it [https://www.gitkraken.com/invite/3pkBJSRn](https://www.gitkraken.com/invite/3pkBJSRn)

### [SourceTree](https://www.sourcetreeapp.com/)

I haven't used it in a while but Sourcetree handles git projects well and is free. My main issue with it is it slows down quite a bit on larger projects or at least it use to.

![gitkrakengif](/assets/img/posts/gitgamedev/hero-mac-screenshot.png){: .image-sized .center-image }  

### [Sublime Merge](https://www.sublimemerge.com/)

This one is new as of October 2018 and is very good. It's free to try and then a flat $99 for a perpetual license.
The only downside for my usage is it does not have a tree view of file changes and instead shows all changes in a flat list. It could keep you from changing to many files at once but at this point I'm use to browsing changes by their folder structure.

![gitkrakengif](/assets/img/posts/gitgamedev/sublimemerge2.gif){: .image-sized .center-image }  

# Online Git Projects

# Github

## Gitlab

## Others

* Bitbucket
* Gitea

# Unity Project Setup