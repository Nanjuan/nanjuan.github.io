---
layout: post
title:  "Github Cheat Sheet"
categories: CheatSheet
authorMain: Nestor N Torres
tag: CheatSheet
description: I made this Github command cheat sheet to have a centralized locaiton for github commands instead of having mutiple links where to look at the commands.
---

### Creating a git develop branch

#### - You can list all of your current branches like this:

`git branch -a`

Example:

```
computer@computer nanjuan.github.io % git branch -a
* develop
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/develop
  remotes/origin/master
```

This shows all of the local and remote branches. Assuming you only have a single master branch, you'd see the following:

```
* develop
  master
```
\* The * means the current branch.

#### - To create a new branch named develop, use the following command:

`git checkout -b develop`

#### - The -b flag creates the branch. Listing the branches now should show:

```
* develop
  master
  remotes/origin/master
Changing branches
```

\* You shouldn't commit anything directly to the master branch. Instead do all your work on the develop branch and then merge develop into master whenever you have a new public release.

#### - You are already in your develop branch, but if you weren't, the way to switch is as follows:

`git checkout develop`

That's the same way you create a branch but without the -b.

Making changes on develop

#### - When making changes, add and commit as usual:

`git add .`

`git commit -m "whatever"`

#### - The first time you push to your remote do it like so:

`git push -u origin develop`
The -u flag stands for --set-upstream. After the first time you only need to do it like this:

`git push`
Merging develop to master

Once your develop is ready to merge into master you can do it like so:

First switch to your local master branch:

`git checkout master`
To merge develop into master do the following:

`git merge develop`
Then push the changes in local master to the remote master:

`git push`
Done.

### Deleting a branch

If you don't need the develop branch anymore, or you just want to delete it and start over, you can do the following:

Delete the remote develop branch:

`git push -d origin develop`
Then delete the local branch:

`git branch -d develop`
The -d means delete.


###### Reference: 
###### https://stackoverflow.com/questions/39478482/how-to-create-development-branch-from-master-on-github
###### https://training.github.com/downloads/github-git-cheat-sheet/

