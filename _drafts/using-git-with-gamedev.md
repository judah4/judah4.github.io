---
layout: post
title:  "Using Git with Game Development"
categories: programming tutorials
---

Source control can be daunting but it is pretty important for sharing with others and backing up to prevent data loss. 
I will cover installing git on a windows environment, using online repositories (repos) and getting a Unity game setup on git.

{% include post-styling.md %}


## Git and What it Does

Pulled from the [site](https://git-scm.com) Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. 
There are other version control systems like subversion but Git is the most popular and widespread.


## Online Git Projects

What's so great about source control and git is you can store your project files online in git repos.

### [Github](https://github.com/)

The most popular online git management website. There are a lot of open source projects hosted here and a good place to collaborate with others.

* Free public repos.
* Limited private repos.

### [Gitlab](https://gitlab.com/)

Gitlab has many of the same features of github.

* Easy to manage private organizations and repos.
* Lots of CI/CD tooling.

### Others

* [Bitbucket](https://bitbucket.org/product) Part of the Atlassian suite.
* [Gitea](https://gitea.io/en-us/) Light and can be self hosted.


## Setup and Visual Git Editors

For windows, we can grab the download right from the git website. https://git-scm.com/download/win  

Following the instructions, it will setup defaults and access to git from the command line. 
This is the default way to use git but I personally use visual editors for commiting and pushing to remote repos.
Once in the install is down you should be able to open the command line or powershell and type in `git --version` and get something like
`git version 2.19.0.windows.1`.
There is a lot of documentation so if you plan on using the command line, [read up](https://git-scm.com/docs).

### Visual editors

I personally use a visual editor. I do have to revert to the commands every once in a while to fix things but for the most part I use visual GUIs.

#### [Gitkraken](https://www.gitkraken.com/git-client)

My preferred git editor. It has a lot of features that I like and is usually fast. 
The free version limits you to one account email and name versus the pro version gives you access to more profiles. 
This is handy so you can commit with different emails between say your work email or your personal email. It has a yearly subscription for the pro features so keep that in mind if you plan on using it.

![gitkraken](/assets/img/posts/gitgamedev/gk-merge-edit.gif){: .image-sized .center-image }  

This is my referral link if you want to sign up and try it [https://www.gitkraken.com/invite/3pkBJSRn](https://www.gitkraken.com/invite/3pkBJSRn)

#### [SourceTree](https://www.sourcetreeapp.com/)

I haven't used it in a while but Sourcetree handles git projects well and is free. My main issue with it is it slows down quite a bit on larger projects or at least it use to.

![source tree](/assets/img/posts/gitgamedev/hero-mac-screenshot.png){: .image-sized .center-image }  

#### [Sublime Merge](https://www.sublimemerge.com/)

This one is new as of October 2018 and is very good. It's free to try and then a flat $99 for a perpetual license.
The only downside for my usage is it does not have a tree view of file changes and instead shows all changes in a flat list. It could keep you from changing to many files at once but at this point I'm accustomed to browsing changes by their folder structure.

![sublime merge](/assets/img/posts/gitgamedev/sublimemerge2.gif){: .image-sized .center-image }  

#### [Github Desktop](https://desktop.github.com/)

Provided by [Github](https://github.com/), a simpler visual git editor.

![github desktop](/assets/img/posts/gitgamedev/github-desktop-screenshot-windows.png){: .image-sized .center-image }
 
## Unity Project Setup

We are starting with these assumptions.

* You have a Github account
* You have a version of Unity installed.
* You have git installed. We will be using Gitkraken with [Github connected](https://support.gitkraken.com/integrations/github/)

To start, we are going to create an empty github project. On the top right of the page there should be a plus button where you can hit [new repository](https://github.com/new).

![new  repo setup](/assets/img/posts/gitgamedev/unity-steps/repo-new.PNG){: .image-sized .center-image }

Once you have the project setup in github, clone in using your git tool. Here, in gitkrake, we have github connected so it can list your porjects and ask you where to download it to.

![repo clone](/assets/img/posts/gitgamedev/unity-steps/repo-clone.PNG){: .image-sized .center-image }


![repo clone github](/assets/img/posts/gitgamedev/unity-steps/repo-clone2.PNG){: .image-sized .center-image }

Once it's ready, it may ask you to initialize the repo if you did not setup a readme file on github. Go ahead and do it.

Next up, we are going to create a unity project in the repo. Go ahead and select the folder to creat it in.

![new unity project](/assets/img/posts/gitgamedev/unity-steps/unity-new.PNG){: .image-sized .center-image }

This will create the unity project one folder level in the git repo folder. In order to have it at the same level as the git repo, you will need to setup the unity project before connecting to the github remote.


Now, before we commit these files, we need to add a git ignore. There are a lot of extra files unity uses that clog up our repo and makes downloading it slow.
Head over to [this page](https://github.com/github/gitignore/blob/master/Unity.gitignore) and create a `.gitignore` file in the unity project folder.

#### Before

![repo changes count](/assets/img/posts/gitgamedev/unity-steps/repo-count.PNG){: .image-sized .center-image }

#### After

![repo changes count after .gitignore](/assets/img/posts/gitgamedev/unity-steps/repo-count2.PNG){: .image-sized .center-image }

Now that we have the files we want we need to commit our changes and push to the remote.

![unity commit gif](/assets/img/posts/gitgamedev/unity-steps/unity-commit.gif){: .image-sized .center-image }

![unity push gif](/assets/img/posts/gitgamedev/unity-steps/unity-push.gif){: .image-sized .center-image }

Now that you pushed your code, your repo  should look something like this.

![unity repo push complete](/assets/img/posts/gitgamedev/unity-steps/repo-fin.PNG){: .image-sized .center-image }

Now that you have source control remember to commit and push often!

### Other Unity tips.

* Don't work on the same scene as other people. They never merge properly.