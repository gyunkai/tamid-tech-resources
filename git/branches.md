# Git Branches

## Why Do We Need Branches?

Branches are essential in Git because they:

- Allow multiple developers to work on different features simultaneously
- Keep the main/production code stable while developing new features
- Enable experimentation without affecting the main codebase
- Make it easier to manage and organize different versions of code
- Facilitate code review and testing before merging changes

## What are Branches?

A branch in Git is simply a pointer to a specific commit. The default branch is called `master`.

## Basic Branch Commands

### View Current Branches

```sh
git branch
```

### Create a New Branch

```sh
git branch <branch-name>
```

### Switch to a Branch

```sh
git checkout <branch-name>
```

## Example Workflow

1. Start with master branch

```sh
git branch
* master
```

2. Create a new branch called 'feature'

```sh
git branch feature
```

3. Switch to the new branch

```sh
git checkout feature
```

4. Now you can make changes and commit them to this branch!

## Tips

- Branches are lightweight
- You can easily switch between branches
- Each branch can have its own commits
- The `HEAD` points to your current branch

## Next Steps

Learn about [working with remotes](remotes.md) to collaborate with others.
