---
layout: post
title:  "Using Git with Game Development"
date:   2019-01-21 9:00:00 -0800
categories: programming tutorials
---

Source control can be daunting but it is pretty important for sharing with others and backing up to prevent data loss. 
I will cover installing git on a windows environment, using online repositories (repos) and getting a Unity game setup with git.

{% include post-styling.md %}


## Git and What it Does

Pulled from the [site](https://git-scm.com), "Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency." 
There are other version control systems like subversion but Git is the most popular and widespread.


## Online Git Projects

You will want a place to push your projects to so check out these online resources.

### [Github](https://github.com/)

The most popular online git management website. There are a lot of open source projects hosted here and a good place to collaborate with others.

* Free public repos.
* Limited private repos.

### [Gitlab](https://gitlab.com/)

Gitlab has many of the same features of Github.

* Easy to manage private organizations and repos.
* Lots of CI/CD tooling.

### Others

* [Bitbucket](https://bitbucket.org/product) Part of the Atlassian suite.
* [Gitea](https://gitea.io/en-us/) Light and can be self hosted.


## Setup and Visual Git Editors

For windows, we can grab the download right from the git website. [https://git-scm.com/download/win](https://git-scm.com/download/win)  

Following the instructions, it will setup defaults and access to git from the command line. 
This is the usual way to use git, but I personally use visual editors for commiting and pushing to remote repos.
Once the install is done, you should be able to open the command line or powershell and type in `git --version` and get something like
`git version 2.19.0.windows.1`.
There is a lot of documentation so if you plan on using the command line, [read up](https://git-scm.com/docs).

### Visual editors

I personally use a visual editor. I do have to revert to the commands every once in a while to fix things, but for the most part I use visual GUIs.

#### [Gitkraken](https://www.gitkraken.com/git-client)

My preferred git editor. It has a lot of features that I like and is usually fast. 
The free version limits you to one account email and name versus the pro version. 
Profiles are handy so you can commit with your personal or work email. 
It has a yearly subscription for the pro features, so keep that in mind if you plan on using it.

![gitkraken](/assets/img/posts/gitgamedev/gk-merge-edit.gif){: .image-sized .center-image }  

#### [SourceTree](https://www.sourcetreeapp.com/)

I haven't used it in a while but SourceTree handles git projects well and is free. 
Also by Atlassian, it integrates well with BitBucket.
My main issue with it is it slows down with larger projects or at least it use to.

![source tree](/assets/img/posts/gitgamedev/hero-mac-screenshot.png){: .image-sized .center-image }  

#### [Sublime Merge](https://www.sublimemerge.com/)

Sublime Merge is new as of October 2018 and is very good. It's free to try and then a flat $99 for a perpetual license.
The only downside for my usage is it does not have a tree view of file changes and instead shows all changes in a flat list.
It's not bad if you keep your changes down to a few files, but at this point I'm accustomed to browsing changes by their folder structure.

Super fast and powerful. Check it out if you use or like Sublime Text.

![sublime merge](/assets/img/posts/gitgamedev/sublimemerge2.gif){: .image-sized .center-image }  

#### [Github Desktop](https://desktop.github.com/)

Provided by [Github](https://github.com/), a simpler visual git editor.

![github desktop](/assets/img/posts/gitgamedev/github-desktop-screenshot-windows.png){: .image-sized .center-image }
 
## Unity Project Setup

We are starting with these assumptions.

* You have a Github account
* You have a version of Unity installed.
* You have git installed. We will be using Gitkraken with [Github connected](https://support.gitkraken.com/integrations/github/).

We will setup projects two ways. Repo first or existing Unity project first.

### 1. New Unity Project and Repo


To start, we are going to create an empty Github project. On the top right of the page there should be a plus button where you can hit [new repository](https://github.com/new).

![new  repo setup](/assets/img/posts/gitgamedev/unity-steps/repo-new.PNG){: .image-sized .center-image }

Once you have the project setup in Github, clone in using your git tool. Here, in GitKraken, we have Github connected so it can list your projects and ask you where to download it to.

![repo clone](/assets/img/posts/gitgamedev/unity-steps/repo-clone.PNG){: .image-sized .center-image }


![repo clone github](/assets/img/posts/gitgamedev/unity-steps/repo-clone2.PNG){: .image-sized .center-image }

Once it's ready, it may ask you to initialize the repo. This happens if you did not setup a readme file on Github. Go ahead and do it.

Next up, we are going to create a unity project in the repo. Go ahead and select the folder to create it in.

![new unity project](/assets/img/posts/gitgamedev/unity-steps/unity-new.PNG){: .image-sized .center-image }

This will create the unity project one folder level in the git repo folder. In order to have it at the same level as the git repo, you will need to setup the unity project before connecting to the Github remote.


Now, before we commit these files, we need to add a `.gitignore`. There are a lot of extra files unity uses that clog up our repo and makes downloading it slow.
Head over to [this page](https://github.com/github/gitignore/blob/master/Unity.gitignore) and create a `.gitignore` file in the unity project folder.

#### Before

![repo changes count](/assets/img/posts/gitgamedev/unity-steps/repo-count.PNG){: .image-sized .center-image }

#### After

![repo changes count after .gitignore](/assets/img/posts/gitgamedev/unity-steps/repo-count2.PNG){: .image-sized .center-image }

Now that we have the files we want, we need to commit our changes and push to the remote.

![unity commit gif](/assets/img/posts/gitgamedev/unity-steps/unity-commit.gif){: .image-sized .center-image }

`git commit --message Basic unity setup.`

![unity push gif](/assets/img/posts/gitgamedev/unity-steps/unity-push.gif){: .image-sized .center-image }

`git push`

Now that you pushed your code, your repo should look something like this.

![unity repo push complete](/assets/img/posts/gitgamedev/unity-steps/repo-fin.PNG){: .image-sized .center-image }

Now that you have source control remember to commit and push often!

### 2. Existing Unity Project
 
It is mostly the same if you are just starting with source control and have an existing project.

Take your existing unity project and open up GitKraken. We will need to init the git project. 
There are ways to setup the remote while initializing but we will add the remote ourselves.

![unity repo push complete](/assets/img/posts/gitgamedev/unity-steps/repo-init.PNG){: .image-sized .center-image }

Go ahead and add the Unity `.gitignore` provided in the drop down or head over to [this page](https://github.com/github/gitignore/blob/master/Unity.gitignore) and create a `.gitignore` file in the unity project folder.

With your `.gitignore`, your changed files should look like this and not include folders like `Library` or `Temp`.

![repo changes count after .gitignore](/assets/img/posts/gitgamedev/unity-steps/repo-count2.PNG){: .image-sized .center-image }

Commit.

![unity commit gif](/assets/img/posts/gitgamedev/unity-steps/unity-commit.gif){: .image-sized .center-image }

And now to setup the remote.

We are going to create an empty Github project. There should be a plus button where you can hit [new repository](https://github.com/new) on the top right of the Github page.

![new repo setup](/assets/img/posts/gitgamedev/unity-steps/repo-new.PNG){: .image-sized .center-image }

**Do not** check the initialize repo with readme. You will have to force push overwriting that content.

Now you should have an empty git repo online. Grab the git url. Mine, for example, is `https://github.com/judah4/unity-game-project2.git`.
On the left of Gitkraken, there is a remote list. Press the `+` and add the new Github remote.

![repo changes count after .gitignore](/assets/img/posts/gitgamedev/unity-steps/repo-remote.PNG){: .image-sized .center-image }

It may ask you to authenticate with Github. This page should help with connecting. [https://support.gitkraken.com/integrations/github/](https://support.gitkraken.com/integrations/github/) 

Now that you have a remote, push and share with others!

![unity push gif](/assets/img/posts/gitgamedev/unity-steps/unity-push.gif){: .image-sized .center-image }

### Other Unity Tips

* Don't work on the same scene as other people. They never merge properly.
* Don't upgrade unity versions right away for an existing project.
* Use and abuse the [asset store](https://assetstore.unity.com/).
* Enjoy making games!

---


If you want to support me and trying out Gitkraken, join through my referral link. [https://www.gitkraken.com/invite/3pkBJSRn](https://www.gitkraken.com/invite/3pkBJSRn)
