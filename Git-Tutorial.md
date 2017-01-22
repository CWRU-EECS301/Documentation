# Git Tutorial

Git can be used from either the command line or from a GUI client application (like GitHub Desktop).  Both have their advantages so it's beneficial to know how to use both types of interfaces.

The command line provides full access to all of Git's functionality and for simple commits can be faster. Complicated branch/merge, remote changes, or nested repos may also be easier from the command line but does require higher level Git expertise.

The GUI clients can make commits with a large number of file changes easier to manage.  Most also have a built in diff tools and can make partial file (hunk) commits possible. When working on multiple feature changes in the same code base, this is invaluable.



## Git from the Command Line

When a Git repository is created or cloned, a single top level directory will be created.  The `git` command can be run from anywhere inside of that directory to operate on the repository. 

The `git` command will give an error if run from outside of a valid Git repository.

Cloning a Git repository inside of another repository should be avoided unless you specifically want to create a Git Submodule.

The most used Git commands are:

* `git status`
* `git clone`
* `git add`
* `git commit`
* `git push`
* `git pull`

Follow this Online Tutorial to learn how to use these commands: [GitHub's tryGit Tutorial](https://try.github.io/)

## GitHub Desktop

After installing the GitHub Desktop, there is a short tutorial pointing out key features.

To learn more about the GitHub Desktop, read through this guide: [Getting Started with GitHub Desktop](https://help.github.com/desktop/guides/getting-started/)


## References

* [GitHub Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
* [Visual Git Cheat Sheet](http://ndpsoftware.com/git-cheatsheet.html)
* [Git Documentation](https://git-scm.com/doc)
