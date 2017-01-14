# Starting Guide to [GitHub](https://github.com)

## Introduction
As a collaboration tool, GitHub allows viewing project code and documentation quickly from a web browser but at some point you'll want to pull the codebase somewhere you can actually work on it.  This guide will help you get your development machine ready to start coding.

## Version Control Basics
We'll be using GitHub for all class projects.  GitHub is a hosting service for Git repositories which provides both direct Git access (via ssh or https) and a very useful web front-end. There are many online resources for both Git and GitHub, a few of which we'll list here.

If you've never used a version control system before, start here with this guide...
[About Version Control](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)

If you've used a VCS before but not git, skip to here in the guide to get an overview of git...
[Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

---
:information_source: As a student, you should consider using GitHub (or a similar service) not only for this class but for all of your classes.  At minimum, it provides a remote backup of all your work in case of a catastrophic event but there are many other benefits:

* Storing class work in a repository organizes everything into a centralized location
* Retain the history of all your files in case you lose something you needed
* Save scanned handouts, tests, notes, etc to have a paperless archive
* Access your work from any computer
* Gain a valuable skill, used in many fields, to list on your résumé

GitHub's [Student Developer Pack](https://education.github.com/pack) offers unlimited private repositories and many other tools free for students.

## GitHub Account Setup

Follow this guide to setup your free GitHub account: [GitHub Account Setup](https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration)

* Pick a professional username (something you'd be happy linking to on a résumé)
* Use your CWRU email account (to be eligible for the Student Developer Pack)
* Choose the **Free** signup option
* Make sure to setup an SSH key for your account: [SSH Access](https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration#SSH-Access)
  * :warning: **Warning:** Be aware that private keys are not secure if you are using a public lab machine. 

Once your personal account is setup:

1. Send your username to the instructor so you can be added to the class team
1. Run thought the [hello-world](https://guides.github.com/activities/hello-world/) tutorial to learn how GitHub works 
1. Optionally, signup for GitHub's [Student Developer Pack](https://education.github.com/pack) (although it's not required for this course)

## Setting Up Your Development Machine
To get started you'll need to configure your machine to use Git.  The setup varies depending on the operating system and each OS has a number of options.

### Windows / macOS(OS X)
[GitHub Desktop](https://desktop.github.com) is available for Windows and Mac and provides both a GUI and command-line tools.  This will be the **recommended option** for this class but feel free to use any other tools available.  Some options are 
[GitKraken](https://www.gitkraken.com),
[SourceTree](https://www.atlassian.com/software/sourcetree) and
[TortoiseGit](https://tortoisegit.org).

Follow this guide for setting up GitHub Desktop: 
[Getting Started with GitHub Desktop](https://help.github.com/desktop/guides/getting-started/)

### Linux
All the major linux distributions have a command-line **git** package that can be installed easily.  For Debian-based distros (e.g. Ubuntu):

```shell
$ sudo apt-get install git-all
```

After installing **git**, there are a number of configuration steps that need to be run only once:

* Set your username and email address

* ```
$ git config --global user.name "YOUR NAME"
$ git config --global user.email "YOUR EMAIL ADDRESS"
```

* Select the default push behavior

* ```
$ git config --global push.default simple
```
