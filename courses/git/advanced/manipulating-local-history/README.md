# Manipulating local history

## Prerequisites

- [Rebasing](/courses/git/basics/rebasing)
- [Inspecting a repository](/courses/git/basics/inspecting)

## Course

Learn about how to use the staging area, and play with your local history.

This includes amending your commits, merging, splitting, removing them.

You should master the interactive rebase (`git rebase -i`).

These parts of Atlassian's git tutorial are a good start:
- [Rewriting history](https://www.atlassian.com/git/tutorials/rewriting-history)
- [Undoing changes](https://www.atlassian.com/git/tutorials/undoing-changes)
- [git reset](https://www.atlassian.com/git/tutorials/undoing-changes/git-reset)

This link explains well some of `git rebase -i`'s usecases: [git interactive rebase](https://robots.thoughtbot.com/git-interactive-rebase-squash-amend-rewriting-history)

Learn what a force push (`git push --force`) is, when it is needed, and what are the dangers using it.

This link explain it well, and presents a very good alternative: [force-with-lease](https://developer.atlassian.com/blog/2015/04/force-with-lease/)

Note that you should **never** rewrite the history of a public branch (a branch used by other people).
