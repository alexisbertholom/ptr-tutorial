# Getting started

## Prerequisites

Before starting, you need to have a github account, and knowing the (very) basics of git and github:
- What is a repository
- Pulling / committing / pushing
- Branches
- Merging / rebasing
- Forking a repository

## Overview

### Goals

This tutorial serves two main purposes:
- Teach you a lot of useful things
- Allow me to follow your progression

### Tree structure

This git repository contains resources and links to resources that will help you learn. They are organized across the directory tree structure, which allows you to pick the themes you want.

Here's an overview of the tree structure:

- `/README.md`:         Summary of the courses, represented as a checklist of your progress
- `/GETTINGSTARTED.md`: The file you're reading now
- `/courses/`:          The directory containing all the courses, subdivised into a logical tree
- `/examples/`:         Examples illustrating some of the courses. Follows the same tree structure as `/courses/`

- `/notes/`:            Your personnal notes. Follows the same tree structure as `/courses/`
- `/playground/`:       Your personnal code snippets / exercises / anything you want to share. Follows the same tree structure as `/courses/`
- `/suggestions/`:      Your personnal suggestions about this tutorial (remarks, improvements, or even new contents)

### Following the tutorial

The way to follow this tutorial is a bit special: you won't just read its content; you'll also contribute to it.
To do this, you will fork this repository (create your own copy of it), so you can edit its contents.

Here are the things that you will be modifying / creating on your local copy of the repository:
- Updating the courses checklist in the `/README.md` file, so your progress can be followed
- Writing down your notes, remarks, reasoning, in the `/notes/` directory
- Sharing code or anything else, in the `/playground/` directory
- Making suggestions or contributing to this repository, in the `/suggestions/` directory

Sharing as much as possible is important, as it will allow you and other people following the tutorial to exchange knowledge, and allow me to help you by checking the quality of your work and giving you tips.

The golden rule of this tutorial is to always understand everything before continuing. If something's not perfectly clear, take the time you need; read it again, search it on the internet, and, if you really need help, ask for it. If some course lacks information, then suggest to add it to the tutorial.


## Detailed Workflow

### Forking the repository

To follow this tutorial, you need to have your own copy of this repository.
Simply go on github, log in, fork this repository.
Just clone your forked repository, and you can start using it !

### Following a course

In the `README.md` file, that you can see on the home page of the repository on github, you can see the list of this tutorial's courses.

Pick the one you want to follow, then follow the associated link. It will lead you to one of `/courses/` subdirectories, containing all the resources relative to this course.

Courses may have prerequisites, please make sure to have them before following the course.

Let's consider the path to the course you are following is `/courses/X/Y/Z`.

First create a branch named `follow-course/X/Y/Z`, which you will use while following this course.
While following the course, you should:
- Take as much notes as needed, put them in the `/notes/X/Y/Z` directory
- Practise a lot, write your own code, and put it in the `/playground/X/Y/Z` directory
- Put the suggestions or remarks you may have in the `/suggestions/X/Y/Z` directory
- Commit and push all the files you created, like described above, on your branch `follow-course/X/Y/Z`

Once you've finished the course:
- Open the `README.md` file.
- Find the line corresponding to the course you were following, which should look like this: `- [ ] Course title [/courses/X/Y/Z](/courses/X/Y/Z)`
- Put an `x` inside the `[ ]`: `- [x] Course title [/courses/X/Y/Z](/courses/X/Y/Z)`. This will check this checkbox on the `README.md`'s courses list. For more information, check [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
- Then commit your changes, and push them to the branch `follow-course/X/Y/Z`.
- Merge your branch `follow-course/X/Y/Z` ([no fast forward !](https://stackoverflow.com/questions/6701292/git-fast-forward-vs-no-fast-forward-merge)) back on `master`
- Then just push the changes you made on the branch `master`, and you're done with this course !

### Pulling changes from the upstream (main) repository

If changes are made on the main repository, you may want to retrieve them and update your copy of the repository.

On your forked repository, configure a remote that points to the upstream repository (https://help.github.com/articles/configuring-a-remote-for-a-fork/).

Let's consider the remote that points to the upstream repository is `upstream`:
- Fetch the latest upstream changes: `git fetch upstream`
- Rebase your local `master` branch onto `upstream/master`, preserving your merges: `rebase --preserve-merges upstream/master master`
- There may be conflicts in the README.md file. Be careful while resolving them !
- After this, your copy of the repository will be up to date with the upstream repository.


## What next ?

You now have all the information you need to start.

- First, check the `Getting started` checkbox in the `README.md`.
- Then, you can pick your first course and start having fun !

You should start with the git courses, as they'll be useful while you follow the tutorial.
