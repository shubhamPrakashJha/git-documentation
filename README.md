<h1 align='center'>

![git Logo](image/git.png)

GIT QUICK REFERENCE GUIDE

</h1>

## Objective

The purpose of this guide is to provide a quick and easy to understand overview of commonly used Git Terms and Git command line instructions for quick reference by both beginers as well as Who want to brush up their Git skills.

Hope this helps. 😀 👍

## Key Terms

### Version Control System (VCS) or Source Code Manager (SCM):

> A VCS allows you to: revert ﬁles back to a previous state, revert the entire project back to a previous state, review changes made over time, see who last modiﬁed something that might be causing a problem, who introduced an issue and when, and more.

### Commit (snapshot):

> Git thinks of its data like a set of snapshots of a mini ﬁle system. Every time you commit, or save the state of your project in Git, it basically takes a picture of what all your ﬁles look like at that moment and stores a reference to that snapshot.

### Repository (repo):

> A directory that contains your project work, as well as a few ﬁles (hidden by default in Mac OS X) which are used to communicate with Git. Repositories can exist either locally on your computer or as a remote copy on another computer.

### Working Directory:

> The ﬁles that you see in your computer's ﬁle system. When you open your project ﬁles up on a code editor, you're working with ﬁles in the Working Directory.

> This is in contrast to the ﬁles that have been saved (in commits!) in the repository.

> When working with Git, the Working Directory is also diﬀerent from the command line's concept of the current working directory which is the directory that your shell is "looking at" right now.

### Checkout:

> When content in the repository has been copied to the Working Directory. It is possible to checkout many things from a repository; a ﬁle, a commit, a branch, etc.

### Staging Area or Staging Index or Index:

> A ﬁle in the Git directory that stores information about what will go into your next commit. You can think of the staging area as a prep table where Git will take the next commit. Files on the Staging Index are poised to be added to the repository.

### SHA:

> A SHA is basically an ID number for each commit. It is a 40-character string composed of characters (0–9 and a–f) and calculated based on the contents of a ﬁle or directory structure in Git. "SHA" is shorthand for "SHA hash". A SHA might look like this:

> `e2adf8ae3e2e4ed40add75cc44cf9d0a869afeb6`

### Branch:

> A branch is when a new line of development is created that diverges from the main line of development. This alternative line of development can continue without altering the main line.

> Going back to the example of save point in a game, you can think of a branch as where you make a save point in your game and then decide to try out a risky move in the game. If the risky move doesn't pan out, then you can just go back to the save point. The key thing that makes branches incredibly powerful is that you can make save points on one branch, and then switch to a diﬀerent branch and make save points there, too.

## GIT COMMANDS

### Create A Git Repo

#### git init

> Create brand new repositories(repos) on your computer

#### git clone

> Copy Existing repos from somwhere else to your local computer

#### git status

> Check the status of the repo

### Review a Repo's History

#### git log

> Display information about the existing commits

#### git show

> Display information about the given commit

### Add Commits To A Repo

#### git add

> Add fies from the working directory to the staging index.

#### git commit

> Tke files from the staging index and saves them in the repository

#### git diff

> Display the difference between two versions of a file

### TAGGING, BRANCHING, AND MERGING

#### git tag

> Add tags to specific commits

#### git branch

> Allows multiple lines of development

#### git checkout

> Switch between different branch and tags

#### git merge

> Combine changes on different branches

### Undoing Changes

#### git commit --amend

> Alter the most-recent commit

#### git revert

> Reverses given commit

#### git reset

> Erases Commits

### Working With Remotes

#### git remote

> Manage Remote Repository

#### git push

> Send changes to the remote

#### git pull

> Retrieve updates from the remote `git pull = git fetch + git merge`

#### gut fetch

> It just retrieves the commits and moves the tracking branch. It does not merge the local branch with the tracking branch.

### Working On Another Developer's Repository

#### Forking a repository

> Forking is an action that's done on a hosting service, like GitHub. Forking a repository creates an identical copy of the original repository and moves this copy to your account.

> You have total control over this forked repository. Modifying your forked repository does not alter the original repository in any way.

#### Reviewing another's developer's change

> discover information about a repository that you're collaborating on with others by grouping and filtering logs.

#### Knowing what to work on

> Before you start doing any work, make sure to look for the project's CONTRIBUTING.md file.

> Next, it's a good idea to look at the GitHub issues for the project
>
> -   look at the existing issues to see if one is similar to the change you want to contribute
> -   if necessary create a new issue
> -   communicate the changes you'd like to make to the project maintainer in the issue

> When you start developing, commit all of your work on a topic branch:
>
> -   do not work on the master branch
> -   make sure to give the topic branch clear, descriptive name

> As a general best practice for writing commits:
>
> -   make frequent, smaller commits
> -   use clear and descriptive commit messages
> -   update the README file, if necessary

### Staying In Sync With A Remote Repository

#### Create a pull request

> A pull request is a request for the source repository to pull in your commits and merge them with their project. To create a pull request, a couple of things need to happen:
>
> -   you must fork the source repository
> -   clone your fork down to your machine
> -   make some commits (ideally on a topic branch!)
> -   push the commits back to your fork
> -   create a new pull request and choose the branch that has your new commits

#### Retrieve and sync updates

> When working with a project that you've forked. The original project's maintainer will continue adding changes to their project. You'll want to keep your fork of their project in sync with theirs so that you can include any changes they make.

> To get commits from a source repository into your forked repository on GitHub you need to:
>
> -   get the cloneable URL of the source repository
> -   create a new remote with the git remote add command
>     -   use the shortname upstream to point to the source repository
>     -   provide the URL of the source repository
> -   fetch the new upstream remote
> -   merge the upstream's branch into a local branch
> -   push the newly updated local branch to your origin repo

#### Develop on an active pull request

> As simple as at may seem, working on an active pull request is mostly about communication!

> If the project's maintainer is requesting changes to the pull request, then:
>
> -   make any necessary commits on the same branch in your local repository that your pull request is based on
> -   push the branch to the your fork of the source repository

> The commits will then show up on the pull request page.

#### Squash Commits

> To squash commits together, we're going to use the extremely powerful `git rebase` command

> The git rebase command is used to do a great many things.

```bash
# interactive rebase
$ git rebase -i <base>

# interactively rebase the commits to the one that's 3 before the one we're on
$ git rebase -i HEAD~3
```

> Inside the interactive list of commits, all commits start out as pick, but you can swap that out with one of the other commands (`reword`, `edit`, `squash`, `fixup`, `exec`, and `drop`).

> I recommend that you create a `backup` branch before rebasing, so that it's easy to return to your previous state. If you're happy with the rebase, then you can just delete the `backup` branch!

<p align='center'>Made with ♥ by Shubham Prakash</p>
