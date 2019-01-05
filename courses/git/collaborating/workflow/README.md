# Workflow

## Prerequisites

- [Branches](/courses/git/basics/branches)
- [Merging](/courses/git/basics/merging)
- [Rebasing](/courses/git/basics/rebasing)
- [Syncing](/courses/git/basics/syncing)
- [Inspecting a repository](/courses/git/basics/inspecting)
- [Manipulating local history](/courses/git/advanced/manipulating-local-history)

## Course

This course will explain the git workflow we use to collaborate.

### Existing git workflows

First, you should have a look at what a workflow is, and some existing ones:

[Comparing workflows](https://www.atlassian.com/git/tutorials/comparing-workflows)

The [Centralized Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows#centralized-workflow) is the most simple one, but is also too limited to be useful.

The [Feature Branch Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow) is the base for more elaborate workflows. Our different workflows are based on this one.

The [Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) is the most elaborate of these workflows. It allows clean managing of the project's releases and features.

The [Forking Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow) is important to know, because it is the one used when contributing to public repositories, by making pull requests from your forked repository.

### Our workflows

Depending on the project, we may use one of 2 different workflows (**Strict** or **Simple**), which will be described later.

Both are based on the Feature Branch Workflow, and both share some rules.

#### General rules

- **We always pull with `git pull --rebase`**. We want to put local commits on top of the commits we may pull. To ensure this behaviour, you can run this: `git config --global branch.autosetuprebase always`. It will always run `git pull` with the `--rebase` option.
- **We always create `feature` branches from the tip (the latest commit) of its parent branch.**
- **Before merging a `feature` branch back to its parent branch, it should be cleaned by amending/merging/splitting local commits if needed**. Interactive rebase (`git rebase -i`) is a particularly useful tool.
- **Before merging a `feature` branch back to its parent branch, we make sure it has been rebased onto the tip of its parent branch.**
- As stated in the last point, a `feature` branch is rebased onto the parent branch before merging. So merging the `feature` branch back to its parent branch at that point would result in a fast-forward. We want to avoid it, so we can have a merge commit. That's why, **when merging a `feature` branch back to its parent branch, we always use `git merge --no-ff`** (no fast-forward).
- **There may be some branches prefixed with `env/`. They represent the version of the project deployed in some environment**. For example, `env/production` represents the version of the project currently in production. Updating one of these branches will automatically deploy new changes.
- **Branches names are always prefixed with one of `feature/`, `refactor/` or `hotfix/`. Special branches, like `master`, are an exception to this rule.** Depending on the workflow used, there may be some more special branches or additional prefixes available. It will be described later.

`refactor/` and `hotfix/` branches, mentionned above, follow the same rules as `feature/` branches.


#### Strict workflow

Our strict workflow is similar to the Gitflow workflow, but with the above set of rules.

We may use this workflow for large projects, where we want to enforce a strict release policy.

As described by Gitflow, there are two special branches: `master` and `develop`.

The following branch prefixes are available: `feature/`, `refactor/`, `hotfix/` or `release/`.

`feature` branches may start either from the `develop` branch, or from other `feature` branches. In this case, the branch is considered as a subfeature, and when over, must be merged back to its parent `feature` branch.

New changes should be committed to a `feature/`, `refactor/`, `hotfix/`, or `release/` branch.

They can, but shouldn't be committed direcly to `develop`.

They must never be committed directly to `master` or some `env/` branch.


#### Simple workflow

Our simple workflow is more permissive, and used for smaller projects.

The `master` branch represents the latest stable version of the project.

`feature` branches may start either from the `master` branch, or from other `feature` branches.

New changes should be committed to a `feature/`, `refactor/`, `hotfix/` branch.

They can, but shouldn't be committed direcly to `master`.

They must never be committed directly to some `env/` branch.
