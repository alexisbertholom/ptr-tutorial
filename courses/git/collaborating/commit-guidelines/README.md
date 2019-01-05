# Commit guidelines

## Prerequisites

- [Overview](/courses/git/basics/overview)

## Course

Every commit made should follow some rules and conventions.

### Commit contents

- A commit should only contain one logical change to the project
- Do not commit change unrelated to your commit (for example, don't implent a feature and do unrelated code formatting in the same commit)
- Big commits should be split into multiple smaller, logical commits
- Group related commits under the same branch
- Useless merge commits are not allowed

### Commit message

Here is the specification we follow for commit messages: [git commit messages](http://karma-runner.github.io/3.0/dev/git-commit-msg.html)

Some small changes we made to this specification:

- The **<scope>** should not be empty (its possible values are relative to the project)
- One additional **<type>** value: `deps`, which is used for commits related to project dependencies (for example, in a JavaScript project, updates to `package.json` or `yarn.lock`)

Reading the message of a commit should be enough to know exactly what it does.